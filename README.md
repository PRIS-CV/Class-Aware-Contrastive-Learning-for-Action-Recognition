# Class-Aware Contrastive Learning for Fine-Grained Skeleton-Based Action Recognition

Code release for "Class-Aware Contrastive Learning for Fine-Grained Skeleton-Based Action Recognition" (ACCV 2024)

![image text](https://github.com/kiiiiid1234/Class-Aware-Contrastive-Learning-for-Action-Recognition/blob/main/src/pic.png)

## Datasets

### FineGym99

The data processing is motivated by https://github.com/kennymckormick/pyskl

### NTU RGB+D

Request dataset: https://rose1.ntu.edu.sg/dataset/actionRecognition

The data processing is motivated by CTR-GCN: https://github.com/Uason-Chen/CTR-GCN

## Train

For FineGym99,

```shell
python main.py --config config/gym/default.yaml --device 0
```

For NTU RGB+D,

```shell
python main.py --config config/nturgbd-cross-subject/joint.yaml --device 0
```

After all modalities, ensemble the results of different modalities, run

```shell
python ensemble.py --datasets ntu/xsub --joint-dir work_dir/ntu60/xsub/ctrgcn_joint --bone-dir work_dir/ntu60/xsub/ctrgcn_bone --joint-motion-dir work_dir/ntu60/xsub/ctrgcn_joint_motion --bone-motion-dir work_dir/ntu60/xsub/ctrgcn_bone_motion
```

## Citation
