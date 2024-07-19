### Use Case: User Registration

#### Id: 1
#### Name: User Registration
#### Description: Users should be able to open a new User account with the Planetarium
#### System: Planetarium application
#### Preconditions:
- No registered user with username "Astronomer"
- Registered user with username "Galileo"
#### Actors:
- User (creating a new account)
- Planetarium application (handles the creation of the new account)

### Scenarios

**Positive Scenario:**
1. Get to the landing page.
2. Pick the option to register.
3. Provide a valid username.
4. Provide a valid password.
5. User should be registered with the Planetarium.

**Negative Scenario Username not unique:**
1. Get to the landing page.
2. Pick the option to register.
3. Provide a non-unique username.
4. Provide a valid password.
5. User should be informed the registration failed.

**Negative Scenario Username too long:**
1. Get to the landing page.
2. Pick the option to register.
3. Provide a username longer than 30 characters.
4. Provide a valid password.
5. User should be informed the registration failed.

**Negative Scenario Password too long:**
1. Get to the landing page.
2. Pick the option to register.
3. Provide a valid username.
4. Provide a password longer than 30 characters.
5. User should be informed the registration failed.

**Negative Scenario credentials too long:**
1. Get to the landing page.
2. Pick the option to register.
3. Provide a username longer than 30 characters.
4. Provide a password longer than 30 characters.
5. User should be informed the registration failed.

**Negative Scenario username taken and password too long:**
1. Get to the landing page.
2. Pick the option to register.
3. Provide a non-unique username.
4. Provide a password longer than 30 characters.
5. User should be informed the registration failed.

### Test Data

**Positive:**
- Valid username: "Astronomer123"
- Valid password: "Celestial@2024"

**Negative:**
- Non-unique username: "Galileo"
- Too long username: "Astronomer_with_a_really_really_long_name"
- Too long password: "ThisIsAVeryLongPasswordThatExceedsThirtyCharacters"

### Decision Table

| Scenario                                     | Username                                  | Password                                  | Result             |
|----------------------------------------------|-------------------------------------------|-------------------------------------------|--------------------|
| Positive Scenario                            | valid username                            | valid password                            | user registered    |
| Negative Scenario Username not unique        | non-unique username                       | valid password                            | user not registered|
| Negative Scenario Username too long          | too long username                         | valid password                            | user not registered|
| Negative Scenario Password too long          | valid username                            | too long password                         | user not registered|
| Negative Scenario credentials too long       | too long username                         | too long password                         | user not registered|
| Negative Scenario username taken and password too long | non-unique username                       | too long password                         | user not registered|

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid username and password, a user should be able to register with the Planetarium | No registered user with username "Astronomer" | valid username, valid password | 1. Get to landing page 2. Pick option to register 3. Provide valid username 4. Provide valid password 5. User should be registered with the Planetarium | User should be registered with the Planetarium | TBD | Tester Name | In Progress |
| 2 | Given a non-unique username and valid password, a user should not be able to register an account | Registered user with username "Galileo" | non-unique username, valid password | 1. Get to landing page 2. Pick option to register 3. Provide non-unique username 4. Provide valid password 5. User should be informed the username is already taken | User not registered | TBD | Tester Name | In Progress |
| 3 | Given a too long username and valid password, a user should not be able to register an account | N/A | too long username, valid password | 1. Get to landing page 2. Pick option to register 3. Provide too long username 4. Provide valid password 5. User should be informed the username is too long | User not registered | TBD | Tester Name | In Progress |
| 4 | Given a valid username and too long password, a user should not be able to register an account | N/A | valid username, too long password | 1. Get to landing page 2. Pick option to register 3. Provide valid username 4. Provide too long password 5. User should be informed the password is too long | User not registered | TBD | Tester Name | In Progress |

---

### Use Case: Secure User Login

#### Id: 2
#### Name: Secure User Login
#### Description: Users should be able to securely access their account.
#### System: Planetarium application
#### Preconditions:
- Registered user with username "Astronomer123" and password "Celestial@2024"
#### Actors:
- User (logging in)
- Planetarium application (handles authentication)

### Scenarios

**Positive Scenario:**
1. Navigate to the login page.
2. Provide a valid username.
3. Provide a valid password.
4. User should be logged into the Planetarium.

**Negative Scenario Invalid password:**
1. Navigate to the login page.
2. Provide a valid username.
3. Provide an invalid password.
4. User should be informed login failed.

**Negative Scenario Username too long:**
1. Navigate to the login page.
2. Provide a username longer than 30 characters.
3. Provide a valid password.
4. User should be informed login failed.

### Test Data

**Positive:**
- Valid username: "Astronomer123"
- Valid password: "Celestial@2024"

**Negative:**
- Invalid password: "WrongPassword"
- Too long username: "Astronomer_with_a_really_really_long_name"

### Decision Table

| Scenario                               | Username                                  | Password                                  | Result             |
|----------------------------------------|-------------------------------------------|-------------------------------------------|--------------------|
| Positive Scenario                      | valid username                            | valid password                            | user logged in     |
| Negative Scenario Invalid password     | valid username                            | invalid password                          | user not logged in |
| Negative Scenario Username too long    | too long username                         | valid password                            | user not logged in |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid username and password, a user should be able to log into the Planetarium | Registered user with username "Astronomer123" | valid username, valid password | 1. Navigate to login page 2. Provide valid username 3. Provide valid password 4. User should be logged into the Planetarium | User should be logged into the Planetarium | TBD | Tester Name | In Progress |
| 2 | Given a valid username and invalid password, a user should not be able to log into the Planetarium | Registered user with username "Astronomer123" | valid username, invalid password | 1. Navigate to login page 2. Provide valid username 3. Provide invalid password 4. User should be informed login failed | User not logged in | TBD | Tester Name | In Progress |
| 3 | Given a username longer than 30 characters and valid password, a user should not be able to log into the Planetarium | N/A | too long username, valid password | 1. Navigate to login page 2. Provide too long username 3. Provide valid password 4. User should be informed the username is too long | User not logged in | TBD | Tester Name | In Progress |

---

### Use Case: View Celestial Bodies

#### Id: 3
#### Name: View Celestial Bodies
#### Description: Users should be able to see planets and moons added to the Planetarium.
#### System: Planetarium application
#### Preconditions:
- User logged in with valid credentials
- Existing planets and moons in the Planetarium
#### Actors:
- User (viewing celestial bodies)
- Planetarium application (displays celestial bodies)

### Scenarios

**Positive Scenario:**
1. User logs in.
2. Navigate to the "View Celestial Bodies" page.
3. User should see a list of planets and moons added to the Planetarium.

### Test Data

**Positive:**
- User credentials: "Astronomer123", "Celestial@2024"

### Decision Table

| Scenario                    | Username                                  | Password                                  | Result                |
|-----------------------------|-------------------------------------------|-------------------------------------------|-----------------------|
| Positive Scenario           | valid username                            | valid password                            | celestial bodies displayed |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid username and password, a user should be able to view planets and moons | Registered user with username "Astronomer123" | valid username, valid password | 1. Log in 2. Navigate to "View Celestial Bodies" page 3. View list of planets

 and moons | User should see a list of planets and moons | TBD | Tester Name | In Progress |

---

### Use Case: Add New Planets

#### Id: 4
#### Name: Add New Planets
#### Description: Users should be able to add new Planets to the Planetarium.
#### System: Planetarium application
#### Preconditions:
- User logged in with valid credentials
#### Actors:
- User (adding new planet)
- Planetarium application (handles planet addition)

### Scenarios

**Positive Scenario:**
1. User logs in.
2. Navigate to the "Add Planet" page.
3. Provide a valid planet name.
4. Submit the planet details.
5. Planet should be added to the Planetarium.

**Negative Scenario Planet name too long:**
1. User logs in.
2. Navigate to the "Add Planet" page.
3. Provide a planet name longer than 30 characters.
4. Submit the planet details.
5. User should be informed the planet name is too long.

### Test Data

**Positive:**
- Planet name: "Earth"

**Negative:**
- Planet name too long: "Planet_with_a_really_really_long_name"

### Decision Table

| Scenario                    | Planet Name                             | Result               |
|-----------------------------|-----------------------------------------|----------------------|
| Positive Scenario           | valid planet name                       | planet added         |
| Negative Scenario Planet name too long | planet name too long                 | planet not added     |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid planet name, a user should be able to add a new planet to the Planetarium | User logged in | valid planet name | 1. Log in 2. Navigate to "Add Planet" page 3. Provide valid planet name 4. Submit planet details | Planet should be added | TBD | Tester Name | In Progress |
| 2 | Given a planet name longer than 30 characters, a user should not be able to add a new planet | User logged in | planet name too long | 1. Log in 2. Navigate to "Add Planet" page 3. Provide planet name too long 4. Submit planet details | User should be informed the planet name is too long | TBD | Tester Name | In Progress |

---

### Use Case: Remove Planets

#### Id: 5
#### Name: Remove Planets
#### Description: Users should be able to remove Planets from the Planetarium.
#### System: Planetarium application
#### Preconditions:
- User logged in with valid credentials
- Existing planets added by the user
#### Actors:
- User (removing planet)
- Planetarium application (handles planet removal)

### Scenarios

**Positive Scenario:**
1. User logs in.
2. Navigate to the "Manage Planets" page.
3. Select a planet to remove.
4. Confirm the removal.
5. Planet should be removed from the Planetarium.

### Test Data

**Positive:**
- Planet to remove: "Earth"

### Decision Table

| Scenario                    | Planet to Remove                             | Result               |
|-----------------------------|----------------------------------------------|----------------------|
| Positive Scenario           | valid planet name                            | planet removed       |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid planet name, a user should be able to remove a planet from the Planetarium | User logged in | valid planet name | 1. Log in 2. Navigate to "Manage Planets" page 3. Select planet to remove 4. Confirm removal | Planet should be removed | TBD | Tester Name | In Progress |

---

### Use Case: Add Moons

#### Id: 6
#### Name: Add Moons
#### Description: Users should be able to add Moons to the Planetarium associated with a Planet.
#### System: Planetarium application
#### Preconditions:
- User logged in with valid credentials
- Existing planets in the Planetarium
#### Actors:
- User (adding new moon)
- Planetarium application (handles moon addition)

### Scenarios

**Positive Scenario:**
1. User logs in.
2. Navigate to the "Add Moon" page.
3. Provide a valid moon name.
4. Select a planet to associate the moon with.
5. Submit the moon details.
6. Moon should be added to the Planetarium.

**Negative Scenario Moon name too long:**
1. User logs in.
2. Navigate to the "Add Moon" page.
3. Provide a moon name longer than 30 characters.
4. Select a planet to associate the moon with.
5. Submit the moon details.
6. User should be informed the moon name is too long.

### Test Data

**Positive:**
- Moon name: "Luna"
- Planet to associate: "Earth"

**Negative:**
- Moon name too long: "Moon_with_a_really_really_long_name"

### Decision Table

| Scenario                    | Moon Name                               | Planet to Associate | Result               |
|-----------------------------|-----------------------------------------|---------------------|----------------------|
| Positive Scenario           | valid moon name                         | valid planet        | moon added           |
| Negative Scenario Moon name too long | moon name too long                   | valid planet        | moon not added       |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid moon name and planet, a user should be able to add a new moon to the Planetarium | User logged in | valid moon name, valid planet | 1. Log in 2. Navigate to "Add Moon" page 3. Provide valid moon name 4. Select valid planet 5. Submit moon details | Moon should be added | TBD | Tester Name | In Progress |
| 2 | Given a moon name longer than 30 characters, a user should not be able to add a new moon | User logged in | moon name too long, valid planet | 1. Log in 2. Navigate to "Add Moon" page 3. Provide moon name too long 4. Select valid planet 5. Submit moon details | User should be informed the moon name is too long | TBD | Tester Name | In Progress |

---

### Use Case: Remove Moons

#### Id: 7
#### Name: Remove Moons
#### Description: Users should be able to remove Moons from the Planetarium.
#### System: Planetarium application
#### Preconditions:
- User logged in with valid credentials
- Existing moons added by the user
#### Actors:
- User (removing moon)
- Planetarium application (handles moon removal)

### Scenarios

**Positive Scenario:**
1. User logs in.
2. Navigate to the "Manage Moons" page.
3. Select a moon to remove.
4. Confirm the removal.
5. Moon should be removed from the Planetarium.

### Test Data

**Positive:**
- Moon to remove: "Luna"

### Decision Table

| Scenario                    | Moon to Remove                             | Result               |
|-----------------------------|--------------------------------------------|----------------------|
| Positive Scenario           | valid moon name                            | moon removed         |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid moon name, a user should be able to remove a moon from the Planetarium | User logged in | valid moon name | 1. Log in 2. Navigate to "Manage Moons" page 3. Select moon to remove 4. Confirm removal | Moon should be removed | TBD | Tester Name | In Progress |
