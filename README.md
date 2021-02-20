# CleanArchitecture_MVVM

Milestone 1: An empty Android App is created.

TODO:

Create an empty Android app (use the Empty Activity template, for example). Save the project on GitHub and make sure to commit and push for each point that is completed. DONE

Add a TextView and an EditText to the screen along with a Button. When the button is activated, the label (TextView) must be updated with the content from the text field (EditText).

Separate data storage from View so that it is stored and maintained in a separate Model class. Place the model class in its own "model" package. The class can, for example, be called "Model". At the same time, place the View class in its own "view" package. For example, the class may be named "AndroidView" (but may also simply remain named as "MainActivity").

Implement Observable functionality for the Model class, so that the label is only updated when the Model class signals that a change has taken place, i.e. as the last in the Model-class set method.

For example, use java.util.Observer and java.util.Observable to implement the Observer pattern. (We see a lot of them being deprecated in Java 9.)

Make sure there is no dependency from the Model class to the View class, i.e. that it must not have direct knowledge of the View class. (It must only know the View class as an Observer.)

Customize the View class to present transformed data in the View. The new functionality will basically wrap the Model class and can, for example, be set to present the model data in a pure lower case.

androidx.lifecycle.MutableLiveData can possibly. is used to facilitate easy Observer functionality in the View class.

Make sure there is still no dependency from the Model class to the View class.

Create a standalone ViewModel class to present transformed data to the View. The specific ViewModel class should basically wrap the Model class and can, for example, be set to present the model data in a pure lower case. In this case, the ViewModel class can be named "LowerCasePresenter". The ViewModel class is placed in the "view" package.

Note that ViewModel technically belongs in the 3rd inner ring of our Clean Architecture. (Because it is a Presenter.) Ie. that ViewModel should not be dependent on a specific UI framework (such as Android). It is therefore necessary to make a different Observable functionality than the one used in pkt. 5.

Make sure there is no dependency from the ViewModel class to the View class and that there is also no dependence from the Model class to the ViewModel class.

Persist data in a database other than Firebase, use SQLite, for example. Be sure to place the database code in a separate "persistence" package. Make sure that the dependencies comply with the guidelines for Clean Architecture, i.e. that Model must not be dependent on anything in the "persistence" package.

Hint: It is necessary to use the Observer pattern to detect when there are changes in Model.

The next time the program is started, it should show the text that was valid when the program was closed.

Replace the database with Firebase. It should be possible to do this without changing the "model" and "view". Separate the two database applications into separate subpackages for "persistence", for example "sqlite" and "firebase".

When several people use the same app at the same time, the text should be updated simultaneously on all devices.

Create a JavaFX project with the same functionality as the Android app. Place the Android View in a separate "view.android" subpackage. It should be possible to reuse everything in the project except the "view.android" package. Place the JavaFX-View in a separate "view.javafx" subpackage.

The user experience should be as described in point 7.

Create a final ViewModel class that will present the model data without transformation, it can for example be named "TrueCasePresenter" and is also placed in the "view" package.

Use the new ViewModel class in the JavaFX app, but not in the Android app. Use the setup to test that the two ViewModels present transformed data without affecting the underlying model.
