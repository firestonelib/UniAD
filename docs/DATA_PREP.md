

# nuScenes
Download nuScenes V1.0 full dataset data, CAN bus and map(v1.3) extensions [HERE](https://www.nuscenes.org/download), following the steps below to prepare the data.


**Download nuScenes, CAN_bus and Map extensions**
```shell
cd UniAD
mkdir data
# Download nuScenes V1.0 full dataset data directly to (or soft link to) UniAD/data/
# Download CAN_bus and Map(v1.3) extensions directly to (or soft link to) UniAD/data/nuscenes/
```

**Prepare UniAD data info**

*Option1: We have already prepared the off-the-shelf data infos for you:*
```shell
cd UniAD/data
mkdir infos
cd infos
wget https://github.com/OpenDriveLab/UniAD/releases/download/v1.0/nuscenes_infos_temporal_train.pkl  # train_infos
wget https://github.com/OpenDriveLab/UniAD/releases/download/v1.0/nuscenes_infos_temporal_val.pkl  # val_infos
```


*Option2: You can also generate the data infos by yourself:*
```shell
cd UniAD/data
mkdir infos
./tools/uniad_create_data.sh
# This will generate nuscenes_infos_temporal_{train,val}.pkl
```

**Prepare Motion Anchors**
```shell
cd UniAD/data
mkdir others
cd others
wget https://github.com/OpenDriveLab/UniAD/releases/download/v1.0/motion_anchor_infos_mode6.pkl
```

**The Overall Structure**

*Please make sure the data structure in UniAD/data/ is as follows:*
```
UniAD
├── projects/
├── tools/
├── configs/
├── ckpts/
│   ├── uniad_base_track_map.pth
├── data/
│   ├── nuscenes/
│   │   ├── can_bus/
│   │   ├── maps/
│   │   ├── samples/
│   │   ├── sweeps/
│   │   ├── v1.0-test/
│   │   ├── v1.0-trainval/
│   ├── infos/
│   │   ├── nuscenes_infos_temporal_train.pkl
│   │   ├── nuscenes_infos_temporal_val.pkl
│   ├── others/
│   │   ├── motion_anchor_infos_mode6.pkl
```
