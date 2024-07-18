### Positive Test Case Scenarios

#### Use Case 1: Users should be able to open a new User account with the Planetarium
- **Id:** 1
- **Name:** User registration
- **Description:** Users should be able to register with the Planetarium
- **System:** Planetarium application
- **Preconditions:** No registered user with username "Stargazer"
- **Actors:** User (creating a new account), Planetarium application (handles the creation of the new account)
- **Positive Use Case Scenario:**
  1. Navigate to the landing page
  2. Select the option to register
  3. Provide a valid username
  4. Provide a valid password
  5. User should be registered with the Planetarium
- **Positive Use Case Scenario Data:**
  - valid username = "Stargazer"
  - valid password = "CosmicVoyager"

#### Use Case 2: Users should be able to securely access their account
- **Id:** 2
- **Name:** User login
- **Description:** Users should be able to securely access their account
- **System:** Planetarium application
- **Preconditions:** Registered user with username "Stargazer" and password "CosmicVoyager"
- **Actors:** User (logging in), Planetarium application (handles the authentication)
- **Positive Use Case Scenario:**
  1. Navigate to the login page
  2. Provide a valid username
  3. Provide a valid password
  4. User should be logged in to the Planetarium
- **Positive Use Case Scenario Data:**
  - valid username = "Stargazer"
  - valid password = "CosmicVoyager"

#### Use Case 3: Users should be able to add new Planets to the Planetarium
- **Id:** 3
- **Name:** Add new Planet
- **Description:** Users should be able to add new Planets to the Planetarium
- **System:** Planetarium application
- **Preconditions:** User logged in with username "Stargazer"
- **Actors:** User (adding a new planet), Planetarium application (handles the addition)
- **Positive Use Case Scenario:**
  1. Navigate to the add planet page
  2. Provide a valid planet name
  3. Optionally provide an associated image
  4. Submit the planet details
  5. Planet should be added to the Planetarium
- **Positive Use Case Scenario Data:**
  - valid planet name = "Earth"
  - associated image = (optional)

### Negative Test Case Scenarios

#### Use Case 1: User registration with non-unique username
- **Id:** 4
- **Name:** Non-unique username
- **Description:** Users should not be able to register with a non-unique username
- **System:** Planetarium application
- **Preconditions:** Registered user with username "Stargazer"
- **Actors:** User (attempting to register), Planetarium application (handles the registration)
- **Negative Use Case Scenario:**
  1. Navigate to the landing page
  2. Select the option to register
  3. Provide a non-unique username
  4. Provide a valid password
  5. User should be informed the username is already taken
- **Negative Use Case Scenario Data:**
  - non-unique username = "Stargazer"
  - valid password = "GalacticWanderer"

#### Use Case 2: User registration with username too long
- **Id:** 5
- **Name:** Username too long
- **Description:** Users should not be able to register with a username longer than 30 characters
- **System:** Planetarium application
- **Preconditions:** N/A
- **Actors:** User (attempting to register), Planetarium application (handles the registration)
- **Negative Use Case Scenario:**
  1. Navigate to the landing page
  2. Select the option to register
  3. Provide a username longer than 30 characters
  4. Provide a valid password
  5. User should be informed the username is too long
- **Negative Use Case Scenario Data:**
  - username too long = "ThisIsAVeryLongUsernameThatExceedsThirtyCharacters"
  - valid password = "GalacticWanderer"

#### Use Case 3: User registration with password too long
- **Id:** 6
- **Name:** Password too long
- **Description:** Users should not be able to register with a password longer than 30 characters
- **System:** Planetarium application
- **Preconditions:** N/A
- **Actors:** User (attempting to register), Planetarium application (handles the registration)
- **Negative Use Case Scenario:**
  1. Navigate to the landing page
  2. Select the option to register
  3. Provide a valid username
  4. Provide a password longer than 30 characters
  5. User should be informed the password is too long
- **Negative Use Case Scenario Data:**
  - valid username = "StarWatcher"
  - password too long = "ThisIsAVeryLongPasswordThatExceedsThirtyCharacters"

#### Use Case 4: User registration with both username and password too long
- **Id:** 7
- **Name:** Username and password too long
- **Description:** Users should not be able to register with both username and password longer than 30 characters
- **System:** Planetarium application
- **Preconditions:** N/A
- **Actors:** User (attempting to register), Planetarium application (handles the registration)
- **Negative Use Case Scenario:**
  1. Navigate to the landing page
  2. Select the option to register
  3. Provide a username longer than 30 characters
  4. Provide a password longer than 30 characters
  5. User should be informed both username and password are too long
- **Negative Use Case Scenario Data:**
  - username too long = "ThisIsAVeryLongUsernameThatExceedsThirtyCharacters"
  - password too long = "ThisIsAVeryLongPasswordThatExceedsThirtyCharacters"

### Decision Table

| Scenario                                   | Username                                     | Password                                     | Result                |
|--------------------------------------------|---------------------------------------------|---------------------------------------------|-----------------------|
| Positive Use Case Scenario                 | valid username                              | valid password                              | user registered       |
| Negative Use Case Scenario Username not unique | non-unique username                          | valid password                              | user not registered   |
| Negative Use Case Scenario Username too long | username too long                            | valid password                              | user not registered   |
| Negative Use Case Scenario Password too long | valid username                              | password too long                            | user not registered   |
| Negative Use Case Scenario credentials too long | username too long                            | password too long                            | user not registered   |
| Negative Use Case Scenario username taken and password too long | non-unique username                          | password too long                            | user not registered   |