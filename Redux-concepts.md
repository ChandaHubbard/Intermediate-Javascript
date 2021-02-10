# Core Redux Concepts

Redux applications are built upon a one-way flow of data model and are managed by the store:
- The state is the set of data values that describes the application. It is used to render the user interface (UI).
- Users interact with the UI which dispatch actions to the store. An action is an object that expresses a desired change to the state.
- The store generates its next state using a reducer function which receives the most recent action and the current state as inputs.
- Finally, the UI is re-rendered based on the new state of the store and the entire process can begin again.
