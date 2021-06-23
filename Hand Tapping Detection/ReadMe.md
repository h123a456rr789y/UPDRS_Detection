# Hand Tapping detection with Mediapipe

Created: Jun 14, 2021 7:52 PM
Status: Complete 🙌
Type: Task 🔨

# Docker environment setup

1. [Install Docker](https://docs.docker.com/get-docker/) on your host system
2. Build a docker image with tag “mediapipe”. But change the Dockerfile to one one we provided !!!

```bash
$ git clone https://github.com/google/mediapipe.git
$ cd mediapipe
$ docker build --tag=mediapipe .
```

3. Run docker image "mediapipe" with the parameter '-v'  to mount path you want 

```bash
docker run -it -v /local_path:/path_in_docker mediapipe
```

4. Move the code and video you want into the folder where you mounted

5. Run the code with following command

```bash
# Example with input_path=current folder, video name = example_left.mp4 and detecting Left hand
python3 hand_detection.py -p . -i example_left.mp4 --hand left 
#Parameters  
-p --path ## input source and output result path //defualt= current folder 
-i, --input_name #Input the video name
--hand # Detect right or left hand(right/left)
																																																																					python3 mediapipe_hand.py 
```

6. Get the final result with an result.txt, result.png and a rusult.mp4

![](https://i.imgur.com/NFMcRFl.png)

- Peak Frame and Tapping Frame:  where the Tapping points(valleys) and the Opening points(peaks) located
- Amplitude: the average distance between  peaks and valleys
- Tapping number: the tapping times
- Action duration: how long does the tapping action last
- Tapping frequency: tapping times / action duration time
- Regularity: Show how regular the patient tap, if regular the give out result will be close to 0
- There will be an output image showing the tapping trajectory , which the red points the tapping points

![](https://i.imgur.com/m4hb8Uz.png)

# Ubuntu 18.04 Environment setup

1. Install Bazelisk. Follow the official Bazel documentation to install Bazelisk.
2. Checkout MediaPipe repository

```bash
$ cd $HOME
$ git clone https://github.com/google/mediapipe.git

# Change directory into MediaPipe root directory
$ cd mediapipe
```

3. Install OpenCV and FFmpeg.

```bash
bash setup_opencv.sh
```


## For other working environment place check the offical mediapipe website for futher installation details

[Mediapipe](https://google.github.io/mediapipe/getting_started/install.html)
