first, install docker
# Either https://docs.docker.com/docker-for-mac/install/
# or
$ brew install docker
# then...
$ docker pull zmkfirmware/zephyr-west-action-arm
$ git clone https://github.com/zmkfirmware/zmk.git
$ cd zmk
$ docker run -w /zmk -v "$PWD:/zmk" zmkfirmware/zephyr-west-action-arm init "-l app"
$ docker run -w /zmk -v "$PWD:/zmk" zmkfirmware/zephyr-west-action-arm update
$ docker run -w /zmk -v "$PWD:/zmk" zmkfirmware/zephyr-west-action-arm update zephyr-export
$ docker run -w /zmk/app -v "$PWD:/zmk" zmkfirmware/zephyr-west-action-arm build "-b nice_nano -- -DSHIELD=sofle_left"

https://github.com/zmkfirmware/zmk/issues/208