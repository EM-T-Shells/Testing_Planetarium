To ensure a total of at least 30 test cases, I will add additional scenarios including Boundary Analysis Testing, Error Guess Testing, and other relevant tests based on the requirements.

---

### Use Case: User Registration

#### Id: 1
#### Name: User Registration
#### Description: Users should be able to open a new User account with the Planetarium
#### System: Planetarium application
#### Preconditions:
- No registered user with username "CarlSagan"
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

**Negative Scenario empty username:**
1. Get to the landing page.
2. Pick the option to register.
3. Provide an empty username.
4. Provide a valid password.
5. User should be informed the registration failed.

**Negative Scenario empty password:**
1. Get to the landing page.
2. Pick the option to register.
3. Provide a valid username.
4. Provide an empty password.
5. User should be informed the registration failed.

**Boundary Analysis Username length 30 characters:**
1. Get to the landing page.
2. Pick the option to register.
3. Provide a username with exactly 30 characters.
4. Provide a valid password.
5. User should be registered with the Planetarium.

**Boundary Analysis Password length 30 characters:**
1. Get to the landing page.
2. Pick the option to register.
3. Provide a valid username.
4. Provide a password with exactly 30 characters.
5. User should be registered with the Planetarium.

### Test Data

**Positive:**
- Valid username: "CarlSagan"
- Valid password: "Cosmos@2024"
- Username 30 characters: "UserWithExactlyThirtyCharacters"
- Password 30 characters: "PasswordWithExactly30Charactrs"

**Negative:**
- Non-unique username: "CarlSagan"
- Too long username: "CarlSagan_with_a_really_really_long_name"
- Too long password: "ThisIsAVeryLongPasswordThatExceedsThirtyCharacters"
- Empty username: ""
- Empty password: ""

### Decision Table

| Scenario                                     | Username                                  | Password                                  | Result             |
|----------------------------------------------|-------------------------------------------|-------------------------------------------|--------------------|
| Positive Scenario                            | valid username                            | valid password                            | user registered    |
| Negative Scenario Username not unique        | non-unique username                       | valid password                            | user not registered|
| Negative Scenario Username too long          | too long username                         | valid password                            | user not registered|
| Negative Scenario Password too long          | valid username                            | too long password                         | user not registered|
| Negative Scenario credentials too long       | too long username                         | too long password                         | user not registered|
| Negative Scenario username taken and password too long | non-unique username                       | too long password                         | user not registered|
| Negative Scenario empty username             | empty username                            | valid password                            | user not registered|
| Negative Scenario empty password             | valid username                            | empty password                            | user not registered|
| Boundary Analysis Username length 30 characters | username 30 characters                    | valid password                            | user registered    |
| Boundary Analysis Password length 30 characters | valid username                            | password 30 characters                    | user registered    |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid username and password, a user should be able to register with the Planetarium | No registered user with username "CarlSagan" | valid username, valid password | 1. Get to landing page 2. Pick option to register 3. Provide valid username 4. Provide valid password 5. User should be registered with the Planetarium | User should be registered with the Planetarium | Passed | Emre | Completed |
| 2 | Given a non-unique username and valid password, a user should not be able to register an account | Registered user with username "CarlSagan" | non-unique username, valid password | 1. Get to landing page 2. Pick option to register 3. Provide non-unique username 4. Provide valid password 5. User should be informed the username is already taken | User not registered | Passed * | Emre | Completed |
| 3 | Given a too long username and valid password, a user should not be able to register an account | N/A | too long username, valid password | 1. Get to landing page 2. Pick option to register 3. Provide too long username 4. Provide valid password 5. User should be informed the username is too long | User not registered | Passed * | Emre | Completed |
| 4 | Given a valid username and too long password, a user should not be able to register an account | N/A | valid username, too long password | 1. Get to landing page 2. Pick option to register 3. Provide valid username 4. Provide too long password 5. User should be informed the password is too long | User not registered | Passed * | Emre | Completed |
| 5 | Given a username and password both too long, a user should not be able to register an account | N/A | too long username, too long password | 1. Get to landing page 2. Pick option to register 3. Provide too long username 4. Provide too long password 5. User should be informed the registration failed | User not registered | TBD | Tester Name | In Progress |
| 6 | Given a non-unique username and too long password, a user should not be able to register an account | Registered user with username "CarlSagan" | non-unique username, too long password | 1. Get to landing page 2. Pick option to register 3. Provide non-unique username 4. Provide too long password 5. User should be informed the registration failed | User not registered | TBD | Tester Name | In Progress |
| 7 | Given an empty username and valid password, a user should not be able to register an account | N/A | empty username, valid password | 1. Get to landing page 2. Pick option to register 3. Provide empty username 4. Provide valid password 5. User should be informed the registration failed | User not registered | TBD | Tester Name | In Progress |
| 8 | Given a valid username and empty password, a user should not be able to register an account | N/A | valid username, empty password | 1. Get to landing page 2. Pick option to register 3. Provide valid username 4. Provide empty password 5. User should be informed the registration failed | User not registered | TBD | Tester Name | In Progress |
| 9 | Given a username with exactly 30 characters and valid password, a user should be able to register an account | N/A | username 30 characters, valid password | 1. Get to landing page 2. Pick option to register 3. Provide username 30 characters 4. Provide valid password 5. User should be registered with the Planetarium | User should be registered with the Planetarium | TBD | Tester Name | In Progress |
| 10 | Given a valid username and password with exactly 30 characters, a user should be able to register an account | N/A | valid username, password 30 characters | 1. Get to landing page 2. Pick option to register 3. Provide valid username 4. Provide password 30 characters 5. User should be registered with the Planetarium | User should be registered with the Planetarium | TBD | Tester Name | In Progress |

---

### Use Case: Secure User Login

#### Id: 2
#### Name: Secure User Login
#### Description: Users should be able to securely access their account.
#### System: Planetarium application
#### Preconditions:
- Registered user with username "CarlSagan" and password "Cosmos@2024"
#### Actors:
- User (logging in)
- Planetarium application (handles authentication)

### Scenarios

**Positive Scenario:**
1. Navigate to the login page

.
2. Provide a valid username.
3. Provide a valid password.
4. User should be logged into the Planetarium.

**Negative Scenario Invalid password:**
1. Navigate to the login page.
2. Provide a valid username.
3. Provide an invalid password.
4. User should be informed login failed.

**Negative Scenario Invalid username:**
1. Navigate to the login page.
2. Provide an invalid username.
3. Provide a valid password.
4. User should be informed login failed.

**Negative Scenario empty username:**
1. Navigate to the login page.
2. Provide an empty username.
3. Provide a valid password.
4. User should be informed login failed.

**Negative Scenario empty password:**
1. Navigate to the login page.
2. Provide a valid username.
3. Provide an empty password.
4. User should be informed login failed.

### Test Data

**Positive:**
- Valid username: "CarlSagan"
- Valid password: "Cosmos@2024"

**Negative:**
- Invalid username: "NeilDegrasseTyson"
- Invalid password: "Galaxy@2023"
- Empty username: ""
- Empty password: ""

### Decision Table

| Scenario                               | Username                                  | Password                                  | Result             |
|----------------------------------------|-------------------------------------------|-------------------------------------------|--------------------|
| Positive Scenario                      | valid username                            | valid password                            | user logged in     |
| Negative Scenario Invalid password     | valid username                            | invalid password                          | user not logged in |
| Negative Scenario Invalid username     | invalid username                          | valid password                            | user not logged in |
| Negative Scenario empty username       | empty username                            | valid password                            | user not logged in |
| Negative Scenario empty password       | valid username                            | empty password                            | user not logged in |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid username and password, a user should be able to log into the Planetarium | Registered user with username "CarlSagan" | valid username, valid password | 1. Navigate to login page 2. Provide valid username 3. Provide valid password 4. User should be logged into the Planetarium | User should be logged into the Planetarium | Passed | Emre | Completed |
| 2 | Given a valid username and invalid password, a user should not be able to log into the Planetarium | Registered user with username "CarlSagan" | valid username, invalid password | 1. Navigate to login page 2. Provide valid username 3. Provide invalid password 4. User should be informed login failed | User not logged in | Passed | Emre | Completed |
| 3 | Given an invalid username and valid password, a user should not be able to log into the Planetarium | Registered user with password "Cosmos@2024" | invalid username, valid password | 1. Navigate to login page 2. Provide invalid username 3. Provide valid password 4. User should be informed the username is invalid | User not logged in | Passed | Emre | Completed |
| 4 | Given an empty username and valid password, a user should not be able to log into the Planetarium | N/A | empty username, valid password | 1. Navigate to login page 2. Provide empty username 3. Provide valid password 4. User should be informed login failed | User not logged in | TBD | Tester Name | In Progress |
| 5 | Given a valid username and empty password, a user should not be able to log into the Planetarium | N/A | valid username, empty password | 1. Navigate to login page 2. Provide valid username 3. Provide empty password 4. User should be informed login failed | User not logged in | TBD | Tester Name | In Progress |

### Notes
* Test Case 2 & 3: User not informed of invalid username or password. Only notified that login attempt failed.

* Upon failed login, the input fields are not cleared.

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

**Negative Scenario Unauthenticated user:**
1. User does not log in.
2. Attempt to navigate to the "View Celestial Bodies" page.
3. User should be informed to log in first.

### Test Data

**Positive:**
- User credentials: "CarlSagan", "Cosmos@2024"

**Negative:**
- Unauthenticated user

### Decision Table

| Scenario                    | Username                                  | Password                                  | Result                |
|-----------------------------|-------------------------------------------|-------------------------------------------|-----------------------|
| Positive Scenario           | valid username                            | valid password                            | celestial bodies displayed |
| Negative Scenario Unauthenticated user | N/A                                       | N/A                                       | login required        |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid username and password, a user should be able to view planets and moons | Registered user with username "CarlSagan" | valid username, valid password | 1. Log in 2. Navigate to "View Celestial Bodies" page 3. View list of planets and moons | User should see a list of planets and moons | Passed | Emre | Completed |
| 2 | Given an unauthenticated user, attempting to view celestial bodies should prompt for login | N/A | N/A | 1. Attempt to navigate to "View Celestial Bodies" page without logging in | User should be informed to log in first | TBD | Tester Name | In Progress |

---

Certainly! Here are additional test cases for adding and removing planets/moons based on the requirements.

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
4. (Optional) Provide an associated image.
5. Submit the planet details.
6. Planet should be added to the Planetarium, owned by the user who added it.

**Negative Scenario Planet name too long:**
1. User logs in.
2. Navigate to the "Add Planet" page.
3. Provide a planet name longer than 30 characters.
4. (Optional) Provide an associated image.
5. Submit the planet details.
6. User should be informed the planet name is too long.

**Negative Scenario Planet name not unique:**
1. User logs in.
2. Navigate to the "Add Planet" page.
3. Provide a non-unique planet name.
4. (Optional) Provide an associated image.
5. Submit the planet details.
6. User should be informed the planet name is not unique.

**Negative Scenario Empty planet name:**
1. User logs in.
2. Navigate to the "Add Planet" page.
3. Provide an empty planet name.
4. (Optional) Provide an associated image.
5. Submit the planet details.
6. User should be informed the planet name is required.

**Boundary Analysis Planet name length 30 characters:**
1. User logs in.
2. Navigate to the "Add Planet" page.
3. Provide a planet name with exactly 30 characters.
4. (Optional) Provide an associated image.
5. Submit the planet details.
6. Planet should be added to the Planetarium.

**Negative Scenario Invalid image format:**
1. User logs in.
2. Navigate to the "Add Planet" page.
3. Provide a valid planet name.
4. Provide an image in an invalid format.
5. Submit the planet details.
6. User should be informed the image format is invalid.

**Negative Scenario Image size too large:**
1. User logs in.
2. Navigate to the "Add Planet" page.
3. Provide a valid planet name.
4. Provide an image that exceeds the maximum allowed size.
5. Submit the planet details.
6. User should be informed the image size is too large.

### Test Data

**Positive:**
- Planet name: "Earth"
- (Optional) Image: "earth.jpg"
- Planet name 30 characters: "PlanetWithExactlyThirtyCharactrs"

**Negative:**
- Planet name too long: "Planet_with_a_really_really_long_name"
- Non-unique planet name: "Earth"
- Empty planet name: ""
- Invalid image format: "earth.txt"
- Image size too large: "earth_large.jpg"

### Decision Table

| Scenario                    | Planet Name                             | Image              | Result               |
|-----------------------------|-----------------------------------------|--------------------|----------------------|
| Positive Scenario           | valid planet name                       | (optional) valid   | planet added         |
| Negative Scenario Planet name too long | planet name too long                 | (optional) valid   | planet not added     |
| Negative Scenario Planet name not unique | non-unique planet name                 | (optional) valid   | planet not added     |
| Negative Scenario Empty planet name | empty planet name                      | (optional) valid   | planet not added     |
| Boundary Analysis Planet name length 30 characters | planet name 30 characters              | (optional) valid   | planet added         |
| Negative Scenario Invalid image format | valid planet name                       | invalid format     | planet not added     |
| Negative Scenario Image size too large | valid planet name                       | too large          | planet not added     |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid planet name, a user should be able to add a new planet to the Planetarium | User logged in | valid planet name, (optional) image | 1. Log in 2. Navigate to "Add Planet" page 3. Provide valid planet name 4. (Optional) Provide an associated image 5. Submit planet details | Planet should be added and owned by the user | TBD | Tester Name | In Progress |
| 2 | Given a planet name longer than 30 characters, a user should not be able to add a new planet | User logged in | planet name too long, (optional) image | 1. Log in 2. Navigate to "Add Planet" page 3. Provide planet name too long 4. (Optional) Provide an associated image 5. Submit planet details | User should be informed the planet name is too long | TBD | Tester Name | In Progress |
| 3 | Given a non-unique planet name, a user should not be able to add a new planet | User logged in | non-unique planet name, (optional) image | 1. Log in 2. Navigate to "Add Planet" page 3. Provide non-unique planet name 4. (Optional) Provide an associated image 5. Submit planet details | User should be informed the planet name is not unique | TBD | Tester Name | In Progress |
| 4 | Given an empty planet name, a user should not be able to add a new planet | User logged in | empty planet name, (optional) image | 1. Log in 2. Navigate to "Add Planet" page 3. Provide empty planet name 4. (Optional) Provide an associated image 5. Submit planet details | User should be informed the planet name is required | TBD | Tester Name | In Progress |
| 5 | Given a planet name with exactly 30 characters, a user should be able to add a new planet | User logged in | planet name 30 characters, (optional) image | 1. Log in 2. Navigate to "Add Planet" page 3. Provide planet name 30 characters 4. (Optional) Provide an associated image 5. Submit planet details | Planet should be added | TBD | Tester Name | In Progress |
| 6 | Given a valid planet name and an invalid image format, a user should not be able to add a new planet | User logged in | valid planet name, invalid image format | 1. Log in 2. Navigate to "Add Planet" page 3. Provide valid planet name 4. Provide invalid image format 5. Submit planet details | User should be informed the image format is invalid | TBD | Tester Name | In Progress |
| 7 | Given a valid planet name and an image that is too large, a user should not be able to add a new planet | User logged in | valid planet name, image too large | 1. Log in 2. Navigate to "Add Planet" page 3. Provide valid planet name 4. Provide image that is too large 5. Submit planet details | User should be informed the image size is too large | TBD | Tester Name | In Progress |

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

**Negative Scenario Unauthorized user:**
1. Another user logs in.
2. Navigate to the "Manage Planets" page.
3. Attempt to remove a planet added by another user.
4. User should be informed they are not authorized to remove this planet.

**Negative Scenario Removing non-existent planet:**
1. User logs in.
2. Navigate to the "Manage Planets" page.
3. Attempt to remove a planet that does not exist.
4. User should be informed the planet does not exist.

### Test Data

**Positive:**
- Planet to remove: "Earth"

**Negative:**
- Unauthorized user
- Non-existent planet: "Mars"

### Decision Table

| Scenario                    | User                  | Planet to Remove                             | Result               |
|-----------------------------|-----------------------|----------------------------------------------|----------------------|
| Positive Scenario           | authorized user       | valid planet name                            | planet removed       |
| Negative Scenario Unauthorized user | unauthorized user  | valid planet name                            | removal not allowed  |
| Negative Scenario Removing non-existent planet | authorized user | non-existent planet                         | removal not allowed  |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid planet name, a user should be able to remove a planet from the Planetarium | User logged in | valid planet name | 1. Log in 2. Navigate to "Manage Planets" page 3. Select planet to remove 4. Confirm removal | Planet should be removed | TBD |

 Tester Name | In Progress |
| 2 | Given an unauthorized user, attempting to remove a planet should fail | Another user logged in | valid planet name | 1. Log in 2. Navigate to "Manage Planets" page 3. Attempt to remove planet 4. Confirm removal | User should be informed they are not authorized to remove this planet | TBD | Tester Name | In Progress |
| 3 | Given a non-existent planet, attempting to remove it should fail | User logged in | non-existent planet | 1. Log in 2. Navigate to "Manage Planets" page 3. Attempt to remove non-existent planet 4. Confirm removal | User should be informed the planet does not exist | TBD | Tester Name | In Progress |

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
5. (Optional) Provide an associated image.
6. Submit the moon details.
7. Moon should be added to the Planetarium, owned by the selected planet.

**Negative Scenario Moon name too long:**
1. User logs in.
2. Navigate to the "Add Moon" page.
3. Provide a moon name longer than 30 characters.
4. Select a planet to associate the moon with.
5. (Optional) Provide an associated image.
6. Submit the moon details.
7. User should be informed the moon name is too long.

**Negative Scenario Moon name not unique:**
1. User logs in.
2. Navigate to the "Add Moon" page.
3. Provide a non-unique moon name.
4. Select a planet to associate the moon with.
5. (Optional) Provide an associated image.
6. Submit the moon details.
7. User should be informed the moon name is not unique.

**Negative Scenario Empty moon name:**
1. User logs in.
2. Navigate to the "Add Moon" page.
3. Provide an empty moon name.
4. Select a planet to associate the moon with.
5. (Optional) Provide an associated image.
6. Submit the moon details.
7. User should be informed the moon name is required.

**Boundary Analysis Moon name length 30 characters:**
1. User logs in.
2. Navigate to the "Add Moon" page.
3. Provide a moon name with exactly 30 characters.
4. Select a planet to associate the moon with.
5. (Optional) Provide an associated image.
6. Submit the moon details.
7. Moon should be added to the Planetarium.

**Negative Scenario Invalid image format:**
1. User logs in.
2. Navigate to the "Add Moon" page.
3. Provide a valid moon name.
4. Select a planet to associate the moon with.
5. Provide an image in an invalid format.
6. Submit the moon details.
7. User should be informed the image format is invalid.

**Negative Scenario Image size too large:**
1. User logs in.
2. Navigate to the "Add Moon" page.
3. Provide a valid moon name.
4. Select a planet to associate the moon with.
5. Provide an image that exceeds the maximum allowed size.
6. Submit the moon details.
7. User should be informed the image size is too large.

### Test Data

**Positive:**
- Moon name: "Luna"
- Planet to associate: "Earth"
- (Optional) Image: "luna.jpg"
- Moon name 30 characters: "MoonWithExactlyThirtyCharacters"

**Negative:**
- Moon name too long: "Moon_with_a_really_really_long_name"
- Non-unique moon name: "Luna"
- Empty moon name: ""
- Invalid image format: "luna.txt"
- Image size too large: "luna_large.jpg"

### Decision Table

| Scenario                    | Moon Name                               | Planet to Associate | Image              | Result               |
|-----------------------------|-----------------------------------------|---------------------|--------------------|----------------------|
| Positive Scenario           | valid moon name                         | valid planet        | (optional) valid   | moon added           |
| Negative Scenario Moon name too long | moon name too long                   | valid planet        | (optional) valid   | moon not added       |
| Negative Scenario Moon name not unique | non-unique moon name                  | valid planet        | (optional) valid   | moon not added       |
| Negative Scenario Empty moon name | empty moon name                      | valid planet        | (optional) valid   | moon not added       |
| Boundary Analysis Moon name length 30 characters | moon name 30 characters              | valid planet        | (optional) valid   | moon added           |
| Negative Scenario Invalid image format | valid moon name                         | valid planet        | invalid format     | moon not added       |
| Negative Scenario Image size too large | valid moon name                         | valid planet        | too large          | moon not added       |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid moon name and planet, a user should be able to add a new moon to the Planetarium | User logged in | valid moon name, valid planet, (optional) image | 1. Log in 2. Navigate to "Add Moon" page 3. Provide valid moon name 4. Select valid planet 5. (Optional) Provide an associated image 6. Submit moon details | Moon should be added and owned by the selected planet | TBD | Tester Name | In Progress |
| 2 | Given a moon name longer than 30 characters, a user should not be able to add a new moon | User logged in | moon name too long, valid planet, (optional) image | 1. Log in 2. Navigate to "Add Moon" page 3. Provide moon name too long 4. Select valid planet 5. (Optional) Provide an associated image 6. Submit moon details | User should be informed the moon name is too long | TBD | Tester Name | In Progress |
| 3 | Given a non-unique moon name, a user should not be able to add a new moon | User logged in | non-unique moon name, valid planet, (optional) image | 1. Log in 2. Navigate to "Add Moon" page 3. Provide non-unique moon name 4. Select valid planet 5. (Optional) Provide an associated image 6. Submit moon details | User should be informed the moon name is not unique | TBD | Tester Name | In Progress |
| 4 | Given an empty moon name, a user should not be able to add a new moon | User logged in | empty moon name, valid planet, (optional) image | 1. Log in 2. Navigate to "Add Moon" page 3. Provide empty moon name 4. Select valid planet 5. (Optional) Provide an associated image 6. Submit moon details | User should be informed the moon name is required | TBD | Tester Name | In Progress |
| 5 | Given a moon name with exactly 30 characters, a user should be able to add a new moon | User logged in | moon name 30 characters, valid planet, (optional) image | 1. Log in 2. Navigate to "Add Moon" page 3. Provide moon name 30 characters 4. Select valid planet 5. (Optional) Provide an associated image 6. Submit moon details | Moon should be added | TBD | Tester Name | In Progress |
| 6 | Given a valid moon name and an invalid image format, a user should not be able to add a new moon | User logged in | valid moon name, invalid image format | 1. Log in 2. Navigate to "Add Moon" page 3. Provide valid moon name 4. Select valid planet 5. Provide invalid image format 6. Submit moon details | User should be informed the image format is invalid | TBD | Tester Name | In Progress |
| 7 | Given a valid moon name and an image that is too large, a user should not be able to add a new moon | User logged in | valid moon name, image too large | 1. Log in 2. Navigate to "Add Moon" page 3. Provide valid moon name 4. Select valid planet 5. Provide image that is too large 6. Submit moon details | User should be informed the image size is too large | TBD | Tester Name | In Progress |

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

**Negative Scenario Unauthorized user:**
1. Another user logs in.
2. Navigate to the "Manage Moons" page.
3. Attempt to remove a moon added by another user.
4. User should be informed they are not authorized to remove this moon.

**Negative Scenario Removing non-existent moon:**
1. User logs in.
2. Navigate to the "Manage Moons" page.
3. Attempt to remove a moon that does not exist.
4. User should be informed the moon does not exist.

### Test Data

**Positive:**
- Moon to remove: "Luna"

**Negative:**
- Unauthorized user
- Non-existent moon: "Phobos"

### Decision Table

| Scenario                    | User                  | Moon to Remove                             | Result               |
|-----------------------------|-----------------------|--------------------------------------------|----------------------|
| Positive Scenario           | authorized user       | valid moon name                            | moon removed         |
| Negative Scenario Unauthorized user | unauthorized user  | valid moon name                            | removal not allowed  |
| Negative Scenario Removing non-existent moon | authorized user | non-existent moon                         | removal not allowed  |

### Test Cases

| Test Case Id | Description | Preconditions | Test Data | Steps | Expected Outcome | Actual Outcome | Tester | Status |
|--------------|-------------|---------------|-----------|-------|------------------|----------------|--------|--------|
| 1 | Given a valid moon name, a user should be able to remove a moon from the Planetarium | User logged in | valid moon name | 1. Log in 2. Navigate to "Manage Moons" page 3. Select moon to remove 4. Confirm removal | Moon should be removed | TBD | Tester Name | In Progress |
| 2 | Given an unauthorized user, attempting to remove a moon should fail | Another user logged in | valid moon name | 1. Log in 2. Navigate to "Manage Moons" page 3. Attempt to remove moon 4. Confirm removal | User should be informed they are not authorized to remove this moon | TBD | Tester Name | In Progress |
| 3 | Given a non-existent moon, attempting to remove it should fail | User logged in | non-existent moon | 1. Log in 2. Navigate to "Manage Moons" page 3. Attempt to remove non-existent moon 4. Confirm removal | User should be informed the moon does not exist | TBD | Tester Name | In Progress |

---