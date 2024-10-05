# DietApp
## components
I wrap the following series of Android Compose components into a class.
+ `RadioButton` (defined in MyRadioButton.kt)
+ `CheckBox` (defined in MyCheckBox.kt)
+ `Button` with `Icon` (defined in MyButtonWithIcon.kt)
+ `AlertDialog` (defined in MyAlertDialog.kt)
+ `DatePicker` (defined in MyDatePicker.kt)
+ `TimePicker` (defined in MyTimePicker.kt)
+ `DropdownMenu` with its items `DropdownMenuItem`(defined in MyDropdownMenu.kt)
+ `LinearProgressIndicator`
+ `CircularProgressIndicator`

While for progress indicator -- `LinearProgressIndicator`, `CircularProgressIndicator`, I provide two modes
+ `Determinate` 
+ `Indeterminate`

In `Determinate` mode, the progress indicator will only run the progress once (such as loading game when opening the app)

In `Indeterminate` mode, it will be indeterminate, the progress indicator will run the progress forever until the flag is set to false (it is set to true at first) through such as interrupt of the thread etc.
