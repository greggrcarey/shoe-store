# Course Notes

8 ways to handle state

Side note: Environment Variables
- Store enviornment-specific settings
- Don't change at runtime
- Supported on all operating systems
- Built into create-react-app
    - REACT_APP_BASE_URL
    - REACT_APP_ENABLE_FEATURE_X

1: URL - Shareable app location
- Current app location/ settings
    - Current item
    - Filters
    - Pagination
    - Sorting 
- Supports deep linking
- Avoid redundant storing in your app
- Consider React Router, a third party option

2: Web Storage - Persist between sessions, one browser
- Persist state between reloads
    - cookies, localStorage, IndexedDB
- Watch out
    - Tied to a single browser
    - Avoid storing sensitive data
- Examples
    - Items in shopping cart
    - Partially completed form data

3: Local State - Only one component needs the state
- Store state inside a React component
    - Useful when one component needs it
- Examples
    - Forms
    - Toggles
    - Local lists

4: Lifted State - A few related components need the state
- Lift state to a common parent
    - Declare state in a parent component
    - Pass the state dwon via props
Use: Related components that need the same state

5: Derived State -  State can be derived from existing state
- Derive state from existing state/props
Examples:
    - Call .length on an array in render
    - Derive errorsExist by checking if the errors array is empty
Why derive?
    - Avoids out of sync bugs
    - Simplifies code

6: Refs - DOM reference, state that isn't rendered
- DOM reference 
    - Uncontrolled components
    - Interfacing with non-React libraries
- State that isn't displayed
    - Track if component is mounted
    - Hold timer
    - Store previous state value

7: Context - Global or subtree state
- Global/ broadly used state and functions
    - Avoids "prop drilling"
- Examples
    - Logged in user
    - Auth settings
    - Theming
    - Internationalization settings

8: Third Party State - Global state, Remote state
- General Options
    - Redux 
    - Mobx
    - Recoil
- Remote State
    - react-query
    - Swr
    - Relay (GraphQL)
    - Apollo (GraphQL)


4 Ways to Handle API Calls
1 - Inline - Call fetch/ Axios/ etc in the component
    - Not recomended 

2 Centralized functions - Create a function in a different file and import it at the top of the file calling the function

3 - Custom hook 
4 - Call library