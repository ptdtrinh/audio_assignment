### audio_assignment
Audio Generation Mixture sound of flute & violin
This repo currently support:

(1) Generate audio by simple mixture of flute and violin using audio data: dummy_mixture.ipynb
(2) Audio-to-Audio Generation (AudioLDM): Given an audio, generate another audio that contain the same type of sound.
(3) Audio-to-Audio Generation (ComMU): generate audio by using only metadata.

## Docker and env settings
# docker
$ docker run -it \
--shm-size 200G \
--runtime=nvidia \
--name 'docker_name' \
pytorch/pytorch:1.10.0-cuda11.3-cudnn8-devel

# make conda env
$ conda create -n audioldm python=3.8
$ pip3 install audioldm

/go/to/path/ComMU-code
$ pip install -r requirements.txt

## Usage
(*) To generate audio by AudioLDM
/go/to/path/AudioLDM
audioldm --file_path simple_flute.wav
audioldm --file_path simple_violin.wav

(*) To generate audio by ComMU 
/go/to/path/ComMU-code
$ python3 generate.py \
--checkpoint_dir {./working_directory/checkpoint_best.pt} \
--output_dir {./output_dir} \
--bpm 70 \
--audio_key aminor \
--time_signature 4/4 \
--pitch_range mid_high \
--num_measures 8 \
--inst acoustic_piano \
--genre newage \
--min_velocity 60 \
--max_velocity 80 \
--track_role main_melody \
--rhythm standard \
--chord_progression Am-Am-Am-Am-Am-Am-Am-Am-G-G-G-G-G-G-G-G-F-F-F-F-F-F-F-F-E-E-E-E-E-E-E-E-Am-Am-Am-Am-Am-Am-Am-Am-G-G-G-G-G-G-G-G-F-F-F-F-F-F-F-F-E-E-E-E-E-E-E-E \
--num_generate 3

Currently the code in this section has error during generation process. Detail of error is mentioned in the report. I will update and fix it soon!
