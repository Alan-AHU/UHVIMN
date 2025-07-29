# UHVIMN
UHVIMN的pytorch实现：通过不确定性引导的历史价值挖掘增强视频中不显著息肉的分割
## Abstract
Accurate segmentation of inconspicuous polyps in video layers is crucial for early colorectal cancer detection. Traditional methods face challenges due to the tiny size, ambiguous boundaries, and light-induced occlusions of these polyps. We propose the Uncertainty-Guided Historical Value Information Mining Network (UHVIMN) to address these issues. UHVIMN comprises three innovative modules: the Dual Similarity-Driven Information Mining Module enhances current frame features by capturing historical value information; the Boundary Self-Awareness Module improves segmentation accuracy for ambiguous boundaries by fusing different features; and the Uncertainty Guided Refinement Module reduces false and missed segmentation by refining high uncertainty regions. Our approach achieved a Dice coefficient of 78.2\%, an IoU of 69.7\%, and an Accuracy of 96.8\% on screened datasets, outperforming six state-of-the-art methods. These results demonstrate UHVIMN's potential as a clinical tool for accurate polyp segmentation, reducing endoscopists' missed diagnosis rates and visual fatigue. Code is available at https://github.com/Alan-AHU/UHVIMN
## 1. Create environment
  + Create conda environment with following command `conda create -n uhvimn python=3.7`
  + Activate environment with following command `conda activate uhvimn`
  + Install requirements with following command `pip install -r requirements.txt`
## 2. Prepare datasets
## 3. Train & Evaluate
### Train
  CUDA_VISIBLE_DEVICES=0 python run/Train.py --config configs/UHVIMN-L.yaml --verbose --debug
### Test 
  # Generate prediction for benchmarks
  python run/Test.py --config configs/UHVIMN-L.yaml --verbose
### Evaluate
  # Evaluate on various metrics
  python run/Eval.py --config configs/UHVIMN-L.yaml --verbose
