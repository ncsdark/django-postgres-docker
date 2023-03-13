# To initialize project if it doesn't exist
docker compose run --no-deps --rm app django-admin startproject app .

# Edit settings.py
# add 0.0.0.0 to ALLOWED_HOSTS and setup DATABASES (see setting.py as example)

# Start containers
docker compose up -d

# Migrate initial django data to db
docker compose exec app python manage.py migrate

# End containers
docker compose down