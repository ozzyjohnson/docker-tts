docker-tts
=============

Quick container for Text To Speech (TTS). Uses eSpeak with MBROLA voices and SoX to generate MP3s from snippets of text.

## Usage

```
docker run \
  -it \
  --rm \
  -v /home/ubuntu:/data ozzyjohnson/tts \
  bash -c 'espeak "The sky above the port was the color of television, tuned to a dead channel." --stdout > gibson.wav'
```

Will encode the provide to test to `WAV`.

```
docker run \
  -it \
  --rm \
  -v /home/ubuntu:/data ozzyjohnson/tts \
  bash -c 'espeak -f moby.txt --stdout | sox -t wav -c 1 - -t mp3 moby.mp3'
```

Will encode to `MP3` in place using the file `moby.txt` as input.

Both examples are mounting a `/home/ubuntu` a data volume. Update the path, text and output type to suit your needs.
