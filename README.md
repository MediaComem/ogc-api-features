# OGC API Features with Node.js, Express, and PostgreSQL

Generic implementation of OGC API Features with Node.js, Express and PostgreSQL

## Step #1

Create a .env file in the root directory and add the following environment variables:

```bash
DB_NAME='<db_name>'
DB_HOST='<host_name>'
DB_PORT= <port_number>
DB_USER='<user_name>'
DB_PASSWORD='<user_password>'
```

## Step #2

Create a `config.yml` file with the informations you want to display for each collection. You can take example on `config.example.yml`.

## Step #3

Install the dependencies running the following command:

`npm ci`

## Step #4

Start the server running the following command:

`node index.js`

__Note:__ For development purposes, you can use `nodemon` to automatically restart the server when a file is changed. To do so, run the following command:

`nodemon index.js`

## Step 5

If you want to have geopose information, add the entries `is_azimuth` (in case you have an azimuth instead of a yaw, the boolean must be `true`. In this case, we convert your azimuth to yaw), `yaw_field`, `roll_field` and `pitch_field` to your configuration file, as in the following example:
```
    providers:
      - type: feature
        name: PostgreSQL
        data:
          schema: public
          id_field: id
          table: images
          geom_field: location
          is_azimuth: true
          yaw_field: azimuth
          roll_field: roll
          pitch_field: tilt
```
