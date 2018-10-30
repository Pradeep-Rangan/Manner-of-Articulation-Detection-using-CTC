# Manner-of-Articulation-Detection-using-CTC
Example on open source An4 dataset
Author: Pradeep R
TCS Research Scholar, Department of Computer Science and Engineering, Indian Institute of Technology (IIT), Kharagpur

Training a manner of articulation CTC detector
1. Install deepspeech pytorch https://github.com/SeanNaren/deepspeech.pytorch
2. Change the text transcriptions of the An4 data such that it contains only manner information
3. Create the labelsManner.json and train the model using standard deepSpeech pytorch


The pre-trained baseline models are saved in 'models/deepspeech_final.pth'

The manner of articulation CTC models are saved in 'modelsAn4Manner/deepspeech_final.pth'

Testing Phase:
Pre-requsite: Run python data/An4.py (of the standard recipie to get the data csv files such as an4_train_manifest.csv and an4_val_manifest.csv)
Now run
python testBaseline.py --val-manifest data/an4_val_manifest.csv --cuda

Expected output is as shown below:
00%|█████████████████████████████████████████████| 7/7 [00:25<00:00,  4.15s/it]
Test Summary 	Average WER 9.314	Average CER 3.782	

To test the manner of articulation CTC models, run:

python testManner.py --val-manifest data/an4_Manner_manifest.csv --cuda

Expected output is as shown below:
100%|█████████████████████████████████████████████| 7/7 [00:27<00:00,  4.45s/it]
Test Summary 	Average WER 7.762	Average CER 2.885	
