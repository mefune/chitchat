# ChitChat



## Prerequisites
- Heroku account
- pgAdmin4

## General Notes
- The project uses Go's new dependency management system.
- For details, see https://blog.golang.org/using-go-modules 


---

## Setup Steps:

#### Step 1:
- Fork this GitHub repo: https://github.com/Ylazerson/chitchat
- Clone it down to your local machine.

#### Step 2:
- Do search (from top dir in repo) for `Ylazerson` and change to your GitHub account name.

#### Step 3:
- Run `go test`
- Run `go mod tidy` (cleans up unused dependencies).
- Check `go.mod` and `go.sum` files to ensure all looks good.
- `go list -m all`


#### Step 4:
- `heroku create`
- This creates a new empty application on Heroku, along with an associated empty Git repository. If you run this command from your app’s root directory, the empty Heroku Git repository is automatically set as a remote for your local repository.
- `git remote -v`
- `git push heroku master`
- Note, the file `Procfile` tells Heroku which command(s) to run to start your app.


#### Step 5:

Add a free Heroku Postgres Starter Tier dev database to your app:
- `heroku addons:create heroku-postgresql:hobby-dev`

Show the `$DATABASE_URL` environment variable:
- `heroku config`

Heroku also provides a `pg` command that shows a lot more:
- `heroku pg`


#### Step 6:
- Add a `.env` file.
- Note, this file is intentionally in `.gitignore`


#### Step 7:
- Run `heroku config` to get the Heroku app name
- Open that app on your Heroku dashboard: https://dashboard.heroku.com/apps
- Open the PostgreSQL add-on for that app.
- View Credentials on the Settings app.
- Create connection in pgAdmin4 using that info.
    - See https://medium.com/@vapurrmaid/getting-started-with-heroku-postgres-and-pgadmin-run-on-part-2-90d9499ed8fb

#### Step 8:
- Using pgAdmin run the `data/setup.sql` script.


#### Git it on up:

```sh

```


---
NOT NEEDED YET:

#### STep ???:
- Set your config variables on Heroku
`heroku config:set REPEAT=10`