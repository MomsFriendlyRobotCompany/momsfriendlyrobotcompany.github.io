# Adafruit Qwiic Sensors for Robotics

# Accelerometer

| Sensor               | Bias (mg)  | Bits | Noise Density (2G) | RMS(mg) @ 100Hz |I2C(Hz)|
|----------------------|------------|------|--------------------|-----------------|-------|
| NXP_FXOS8700CQ       | 20         | 14   | 126                | 1.11636         | 100k  |
| [LSM6DS33][id8]      | 40         | 16   | 90                 | 0.797402        | 100k  |
| [LSM6DSOX][id2]      | 20         | 16   | 70                 | 0.620202        | 1M    |
| LSM6DS3TR            | 40         | 16   | 90                 | 1.7             | 400k  |
| [ISM330DHCX][id4]    | 10         | 16   | 60                 | 1.8             | 1M    |
| LSM9DS1              | 90         | 16   | 200                | 1.772           | OLD   |
| ICM-20649            | Unkn       | 16   | 285                | 2.52511         |       |
| ICM-20948            |            | 16   | 230 (10Hz)         |                 | 400k  |
| [ICM-42688-P][id7]   | 20         | 16   | 70                 | 0.70            | 1M    |
| [BNO055][id5]        | 80         | 14   | 150                | 1.329           |       |
| [BNO085][id6]        |            |      |                    |                 | 400k  |
| MPU6050              | 50/80      | 16   | 400                |                 | 400k  |

- Bias: Linear acceleration zero-g level offset accuracy
- Noise Density: $\mu g / \sqrt{Hz}$

[id2]: https://www.st.com/resource/en/datasheet/lsm6dsox.pdf
[id4]: https://www.st.com/resource/en/datasheet/ism330dhcx.pdf
[id5]: https://cdn-learn.adafruit.com/assets/assets/000/125/776/original/bst-bno055-ds000.pdf?1698865246
[id6]: https://www.ceva-dsp.com/wp-content/uploads/2019/10/BNO080_085-Datasheet.pdf
[id7]: https://invensense.tdk.com/wp-content/uploads/2020/04/ds-000347_icm-42688-p-datasheet.pdf
[id8]: https://www.st.com/resource/en/datasheet/lsm6ds33.pdf

# Orientation

| Sensor               | I2C  | Notes |
|----------------------|------|---|
| [BNO055][o1]         | `0x28` |   |
| [BNO085][o2]         | `0x4A`,`0x4B` | Vendor sold to new company |

[o1]: https://www.adafruit.com/product/4646
[o2]: https://www.adafruit.com/product/4754

**WARNING:** these use Andriod/iOS definitions of coordinate systems 
and not standard aerospace definitions of the frame (x-forward, y-right wing, z-down)

# Gryoscope

| Sensor               | Bits  | Noise Density | Drift | RMS(mdps) @ 100Hz | Zero | ODR |
|----------------------|-------|---------------|-------|-------------------|------|-----|
| [NXP_FXAS21002C][i1] | 16    | 25            | 0.02  | 223.607           | 0.52 |
| [LSM6DS33][i2]       | 16    | 7             | 0.05  | 62.6099           | 1.3  |
| [LSM6DSO(X)][i3]     | 16    | 3.8           | 0.01  | 33.9882           | 0.26 |
| [LSM6DS3TR][i8]      |       | 5             | 0.05  | 75                | 0.05 |
| [ISM330DHCX][i4]     | 16    | 5             | 0.005 | 44.7214           | 0.13 |
| [MPU6050][i9]        | 16    | 0.005 (10Hz)  | 20    | 50                |      |
| [ICM-20948][i10]     | 16    | 15            | 0.05  |                   | 5    |
| ICM-42688-P          | 16    | 2.8           | 0.05  | 28                | 0.5  |

- Drift: Angular rate typical zero-rate level change vs. temperature (dps/C)
- Zero: Initial Zero Tolerance @ 25C
- Noise Density: $mdps/ \sqrt{Hz}$

[i1]: https://www.adafruit.com/product/3463
[i2]: https://www.adafruit.com/product/4485
[i3]: https://www.adafruit.com/product/4517
[i4]: https://www.adafruit.com/product/4502
[i5]: https://www.adafruit.com/product/4634
[i6]: https://www.adafruit.com/product/4464
[i7]: https://www.adafruit.com/product/4646
[i8]: https://www.adafruit.com/product/4503
[i9]: https://www.adafruit.com/product/3886
[i10]: https://www.adafruit.com/product/4554

# Magnetometer

Earth's magnetic field ranges between 0.25 and 0.65 gauss (25 - 65 $\mu$T)

| Sensor          | Bits | Scale ($\pm$ gauss) | RMS(mgauss)      | ODR (Hz)         | LSB/C | Bias ($\pm$ mG) |SPI(MHz)| I2C(Hz) | Addr        |
|-----------------|------|---------------------|------------------|------------------|-------|----------------|--------|--------|-------------|
|[LIS3MDL][ds1]   | 16   | 4,8,12,16           | 3.2 (@ 12 gauss) | 155,300,560,1000 | 8     | 1 (@ 4 gauss)  | 10     | 400k   |`0x1C`,`0x1E`
|[LIS2MDL][ds2]   | 16   | 50                  | 4.5 (Hi Res)     | 10,20,50,100     |0.3mg/C| 60             | 10     | 3400k  |`0x1E`
|[MMC5603NJ][ds3] | 20   | 30                  | 2 (@ 150Hz)      |                  | Unk   |                | N/A    | 400k   |`0x30`
|[QMC5883L][ds4]  | 16   | 2,8                 | unknown          | 10, 50, 100, 200 | 100   | 10             | N/A    | 400k   |`0x1D`
|[LSM303DLHC][ds5]| 16   | 1.3-8.1             | unknown          | 15,30,75,220     | Unk   | 20             | N/A    | 400    | `0x19`
|[LSM303AGR][ds6] | 16   | 50                  | 3                | 10,20,50,100     | 3     |                | 10     | 3400k  | `0x19`
|[MLX90393][ds7]  | 19   | 50-500              |~50 (1.61 mgauss/LSB)| 1-700 (complex)  | 45.2  | 0?             | 10     | 3400k  | many

- Temperature drift centered at 25C
- LIS3MDL can have slower ODR (0.625-80Hz) when `FAST_ODR` is set low in `CTRL_REG1`

[ds1]: https://www.st.com/resource/en/datasheet/lis3mdl.pdf
[ds2]: https://www.st.com/resource/en/datasheet/lis2mdl.pdf
[ds3]: https://cdn-learn.adafruit.com/assets/assets/000/113/957/original/MMC5603NJ_RevB_7-12-18.pdf
[ds4]: https://www.qstcorp.com/en_comp_prod/QMC5883L
[ds5]: https://www.st.com/resource/en/datasheet/lsm303dlhc.pdf
[ds6]: https://www.st.com/resource/en/datasheet/lsm303agr.pdf
[ds7]: https://www.melexis.com/en/documents/documentation/datasheets/datasheet-mlx90393

# Pressure

| Sensor         | bits | ODR (Hz)      | Abs Accuracy (Pa) | Rel Accuracy (Pa) | Range (hPa) |SPI(MHz)| I2C (Hz) | Addr      |
|----------------|------|---------------|-------------------|-------------------|-------------|--------|----------|-----------|
| [LPS22][gds3]  | 24   | 1,10,25,50,75 | 100               | Unknown           | 260-1260    | 10     | 400k     |`0x5C`,`0x5D`      
| [DPS310][gds1] | 24   | 128           | 100               | 6 (0.55m)         | 300-1200    |        | 3.4M     |`0x76`,`0x77`
| BMP388         | 24   | 200           | 50                | 8 (0.66m)         | 300-1100    |        | 3.4M     |     
| [BMP390][gds2] | 24   | 25,50,100,200 | 50                | 3 (0.25m)         | 300-1250    | 10     | 3.4M     |`0x76`,`0x77`

[gds1]: https://www.infineon.com/dgdl/Infineon-DPS310-DataSheet-v01_01-EN.pdf?fileId=5546d462576f34750157750826c42242
[gds2]: https://www.bosch-sensortec.com/media/boschsensortec/downloads/datasheets/bst-bmp390-ds002.pdf
[gds3]: https://www.st.com/resource/en/datasheet/dm00140895.pdf

[Altitude][peqn] can be calculated with:

$$
\begin{align*}
altitude &= \frac{T_0}{L} \left( \frac {p}{P_0} ^ {\frac{-R L}{g_0 M}} - 1.0 \right) \\
         &= 44330 [1-\frac{p}{P_0}^{\frac{1}{5.255}}]
\end{align*}
$$

where 

| Symbol | Description | Value |
|--------|-------------|-------|
| $P_0$ | Pressure at sea level     | 101325 Pa |
| $T_0$ | Temperature at sea level  | 288.15 K |
| $R$   | Universal gas constant    | 8.31446261815324 Nm/(mol K) |
| $M$   | Molar mass of Earth's air | 0.0289644 kg/mol |
| $g_0$ | Gravitational constant    | 9.80665 m/s^2 |
| $L$   | Lapse rate                | -0.0065 K/m |

[ref](https://www.mide.com/air-pressure-at-altitude-calculator)

[peqn]: https://cdn-shop.adafruit.com/datasheets/BST-BMP180-DS000-09.pdf
[p1]: https://www.adafruit.com/product/4633
[p2]: https://www.adafruit.com/product/4494
[p3]: https://www.adafruit.com/product/4816
[p4]: https://www.adafruit.com/product/3966

## GPS

| Sensor  | Addr   | Rate             | Datasheet |
|---------|--------|------------------|-----------|
| PA1010D | `0x10` | 400 (unverified) | [datasheet][gps1]

[gps1]: https://cdn-learn.adafruit.com/assets/assets/000/084/295/original/CD_PA1010D_Datasheet_v.03.pdf?1573833002

## Miscellanious I2C (QWIIC) Parts

| Device | Part | I2C |
|--------|------|-----|
| LED backpack | [HT16K33][misc1]   | 400k |
| NFC/RFID     | [ST25DV16K][misc2] | 1M   |

[misc1]: https://cdn-shop.adafruit.com/datasheets/ht16K33v110.pdf
[misc2]: https://cdn-learn.adafruit.com/assets/assets/000/093/906/original/st25dv04k.pdf?1596828496

## Wiring

![](./qwiic-pinout.jpg)

- Red: 3.3VDC Power
- Black: Ground
- Blue: I2C SDA Data
- Yellow: I2C SCL Clock




