Code is adapted from the fair-seq library https://github.com/facebookresearch/fairseq - specifically the speech_to_text_joint_to_text example in /examples. 

pre-training_mine.md in /examples/speech_to_text_joint_to_text/docs has instructions on how to prepare the data and run the code including our adaptations. There are several other adaptations throughout the /fairseq library all adapted files end in _mine.py. Note that the --task, --criterion and --arch (architecture) options in pre-training.md all end in _mine also. 

The adaptations change model training and architecture to match the diagram included in the draft report, adapted from figure 1 b) here: https://arxiv.org/pdf/2204.05409.pdf. The adaptations are focused on removing the assumptions of the availability of:
1) Parallel speech to text translation data in the low resource language,
2) Forced alignment supervised data for either language,
3) Phoneme encoding for either language,
as these assumptions are unrealistic for low resource languages. Additional auxiliary losses are added to the speech encoder to make the training of the encoder more robust under limited data scenarios. 

