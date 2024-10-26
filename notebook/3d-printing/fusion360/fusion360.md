# Fusion 360

## Shortcuts

| Key | [Shortcut Description](https://www.autodesk.com/shortcuts/fusion-360) |
|:---:|---|
| C | Draw center circle |
| D | Dimension |
| E | Extrude |
| F | Fillet |
| I | Measure |
| J | Joint |
| Shift-J | As built joint |
| L | Line |
| M | Move |
| P | Project |
| T | Text |
| X | Normal/construction line toggle | 


## Notes

- Preferences
    - General: :white_check_mark: Reverse zoom direction
- 3D printing
    - File -> Export -> save as a `*.3mf`
    - STL is old crap ... 3MF is a better format
- Dimensions
    - Rotate a line in global coordinates
        - Make origin visible
        - Enter sketch mode
        - Using `shift`, select origin axis and then the line you want
        - Create -> Dimension
            - Should see and angular dimension arrow appear, click and set desired angle
- Cross Section Inspection Analysis
    - Select a plane or object surface
    - Utilities -> Inspect -> Section analysis
        - Adjust the cutting plane until you get the cross section you want and press Enter
- Parameterize
    - modify -> fx Change Parameters
        - click `+` under User Parameters and create new parameter
        - Now use in sketch for dimensions
        - Any updates to these parameters will regenerate the model with new dimensions
- [Revolute Joint](https://help.autodesk.com/view/fusion360/ENU/courses/AP-ASSEMBLIES-AND-JOINTS)
    - Select assemble -> Joint  (or shortcut `j`)
        - This only works with Components
    - Select `Revolute` for motion type
    - Select the pin diameter first
    - Select the hold diameter second
    - <table><tr><td><img src="pics/pin.jpg" height="200px"></td><td><img src="pics/hole.jpg" height="200px"</td></table>
    - Preview animation
        - Note: the pin may move to the hole, but that is not necessarily where it will go to
    - Select OK
- [Global Parameters](https://productdesignonline.com/how-to-create-and-use-global-parameters-in-fusion-360/)
    - Create new "Master Parameter" project with whatever parameters you need
    - Favorite each parameter :star:
    - Save project
    - `Create` -> `Derive` -> select `Favorites` -> **New** or **Existing Project** (if you forget to do this *first*)
    - In the derived project, you must scroll to the bottom of the parameter dialog and favorite what parameters you want to use
    - Updating the "Master Parameter" project will show an update icon in the derived project (near the Save File icon)
    - **Adding to an Existing Project**:
        - `INSERT` -> `Insert Derive`
        - **Info:** don't freak out, but a new Parameter-Master tab will open, but once you are done, it will close
        - scroll down and select `Favorites`
        - select `OK`
- [Import F3D File into Current Design](https://forums.autodesk.com/t5/fusion-360-design-validate/how-to-insert-a-f3d-file-into-an-existing-project/m-p/8870972/highlight/true#M192398)
    - Fusion360 -> File -> Open -> save to cloud
        - Can mark "Read-Only" to save 
    - Open Data panel with all cloud designs
    - right click on design you just saved -> Insert into Current Design
