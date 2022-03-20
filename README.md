# SQL Music Synthesiser

Using PostgreSQL to synthesise Twinkle Twinkle Little Star.

## Getting Started

Clone the repository or download `synthesiser.sql`. Run the SQL code to recreate the table and views. Feel free to tweak the table `music_sheet` to play any other melody.

To generate the WAV file, run the bash command below.

```bash
psql -U postgres -qAt -c "select encode(file,'base64') from v_wav limit 1" | base64 -d > /tmp/twinkletwinkle.wav
```
If you don't have a PostgreSQL environment set up, you can spin one up via Docker using the official image "postgres" as shown below. Note that this server won't be secured.

```bash
docker run -e POSTGRES_HOST_AUTH_METHOD=trust  -p 5432:5432 postgres
```

Once you've created the file, you can copy the file out of Docker with the following command.

```bash
docker cp container_name:/tmp/twinkletwinkle.wav twinkletwinkle.wav
```

## Authors

* **Ramiro Medina**

## License

This project is licensed under the MIT License.
