# About this repository
- This repository is made for running [PC6001VX](https://github.com/eighttails/PC6001VX) via docker container.
- PC6001VX is made with [Qt Creator](https://www.qt.io/product/development-tools), thats why it is advisable to run the app via docker, not installing to your host computer.
- But the running GUI app and making the audio active from the docker container is a little bit tricky, but I guess I found the solution.
- First of all, download my source code from this repository, then go to the following procedure.

## Procedure

1. Download the latest source code from [PC6001VX](https://github.com/eighttails/PC6001VX) repository, then unzip it followed by put the folder to `./pc6001vx/workdir/`
2. @this project's root directory (where `docker-compose.yml` exists), run the following command.
    ```
    $ docker compose up -d
    $ docker exec -it <container name> bash
    ```
3. You are now inside the docker container. Move to the source code directory.
    ```
    $ cd <souece code directory name>
    ```
4. Run the compile commands
    ```
    $ qmake6 PC6001VX.pro
    $ make
    ```
5. Run the app (make sure you are inside the source code directory)
    ```
    $ ./PC6001VX
    ```
6. At the first time of lauch, you will be asked about rom files location, and just select "NO" this time
7. At the first time of lauch, you will be asked about built in rom files, and just select "NO" this time
8. Put your rom files into `./pc6001vx/.pc6001vx4/rom/` (your host computer directory)
9. Run the app again
    ```
    $ ./PC6001VX
    ```
10. To finish Today's PC6001VX life, `exit` the docker container then,
    ```
    docker compose down
    ```
11. To resume Yesterday's PC6001VX life, just do the followings
    ```
    $ docker compose up -d
    $ docker exec -it <container name> bash
    $ cd <souece code directory name>
    $ ./PC6001VX
    ```

## References
https://github.com/mviereck/x11docker/wiki/Container-sound:-ALSA-or-Pulseaudio  
https://qiita.com/Light606F/items/898081a73166c010473a  
