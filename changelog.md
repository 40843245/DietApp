# Diet App
## changelog
### v1.0.0

at 2024/10/3 20:30

#### functionalities

+ Under the package `com.example.dietapp.util.components`, I customize some Android Compose components into class. Including
  - AlertDialog
  - DropdownMenu
  - DatePicker
  - TimePicker
  
+ Under the package `com.example.dietapp.util.queryhandling`, it is easily to dynamically generate some basic MySQL statements.

Additionally, I think it is flexible to use, maintenable (i.e. easier to modify the code once the feature changes), and extensible (i.e. easier to extend the functionalities with fewer code)

+ Under the package `com.example.dietapp.extension.string`, I create some extension function for String type in Kotlin.

+ For more functionalities, see [functionality.md](https://github.com/40843245/DietApp/blob/main/functionality.md)
  
#### caution
> [!CAUTION]
> Be aware when use these generated MySQL statement to query results with driver for database (such as JDBC).
>
> Also be aware of SQL injection (an attack through give some invalid input so that generates a SQL statement that may result in unexpected behaviour such as generates a MySQL statements
>
> `SELECT * FROM user WHERE username = 'username1;' OR password LIKE '%%%%';`)
>
> There is no such functionality to check the syntax of MySQL statement.
>
> If one passed a garbage value into argument, one may get a garbage MySQL statement. Motto: GIGO (stands for Garbage In Garbage Out).
>
> For example: One passed `table#$%^%1` into argument to set the table name. There are no cautions or exception etc. And may generate a garbage MySQL statement when building. Shown as follows, causing unexpected behaviour.
>
> ```
> SELECT * FROM `table#$%^%1`;
> ```

### v1.0.1
at 2024/10/3 21:21 

#### added
+ I added the comments as documentation.
+ I refactor the folder and category the folder and file again.

### v2.0.0
at 2024/10/4 15:33
#### fixed
+ Under the package `com.example.dietapp.util.components`, I fix the bug of these class about some Android Compose components that I customized. Including
  - AlertDialog
  - DropdownMenu
  - DatePicker
  - TimePicker
 
through change the some property of class from non `MutableState` to `MutableState`.

such as `val checked:Boolean` into `val checked:MutableState<Boolean>`

so that one can access the updated value outside of the class declaration itself (such as on the level of instance of instantiation).

Before this version, one can only access the updated value inside of the class declaration itself. 

If one want to access the update value outside the class declaration, one has to access the property of the class.

For more details, compare the code between version `v1.0.1` and `v2.0.0`.

#### added
+ Wrap these Android Compose components into class.
  - CheckBox
    
#### deleted
1. Unused package.

### v2.1.0
at 2024/10/4 16:39

#### added
Add the property `selectableDates` in `MyDatePickerDialog` class, the property `selectableDates` determines whether the date can be selected.

In older version,

```
class MyDatePickerDialog(
    private val buttonText:String,
    private val modifier: Modifier = Modifier.height(40.dp).fillMaxWidth(),
    private val onDateSelected: (String) -> Unit,
)
```

While in this version,

```
class MyDatePickerDialog @OptIn(ExperimentalMaterial3Api::class) constructor(
    private val buttonText:String,
    private val modifier: Modifier = Modifier.height(40.dp).fillMaxWidth(),
    private val onDateSelected: (String) -> Unit,
    private val selectableDates: SelectableDates? = null
)
```

### v2.2.0
at 2024/10/5 15:10

#### added
Wrap a series of components and add its corresponding class.

+ progress indicator
  - `LinearProgressIndicator`
  - `CircularProgressIndicator`

+ button
  - button with icon
  - `CheckBox`


While for the wrapper class of progress indicator, I provide two modes

+ `Determinate`
+ `Indeterminate`

For more details, see [components section in components.md](https://github.com/40843245/DietApp/blob/main/components.md#components)

#### change
1. extract the pattern of date into `DateFormatterPattern.kt` file, making it more maintenable.
