# Starting Keycloak

You need to pull the `environment` repository.

## Starting the database

```
cd database
sudo rm -rf keycloak-db
./start-keycloak-db.sh
```

## Importing the realm

```
cd identity-provider
./setup-keycloak.sh
```

After you see this log:
```
Running the server in development mode. DO NOT use this configuration in production.
```

Press CTRL-C to stop the container. Then:

```
./start-keycloak.sh
```

## Configuring users

Go to: https://bitfever-server:8443/auth and login using the following credentials:
- Username: keycloak-admin
- Password: keycloak#admin

### Creating a normal user

After login, select the **bitfever** realm. We need to create an admin user (`admin`) and a generic user
(`user`). Click `Users` on the left and then the "Add user" button. Use the following settings:

- Email verified = yes
- Username       = user
- First name     = User
- Last name      = User

Then, click `Create`. Now, on the user tab, click `Credentials` and then `Set password`. Use the following settings:
- Temporary = Off
- Password = bf#user

Click `Save` and then the `Save password` button.

Now, click `Role mapping`, then `Assign role` and select the `User` role.

### Creating an administrator

Use the same process described above to create the `admin` user. Use:
- Username       = admin
- First name     = Admin
- Last name      = Admin
- Password = bf#admin
- Role = admin
