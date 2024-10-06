>[!Under construction with Masahiro Jiang]
>We aim to make it work with our spatial navigation task + visual stimuli from NPX1 and 2
>Everything is single cluster oriented - what a cluster has during the recordings

## Final Format
For single neurons (spike sorted from AP data):
>==`/data/clusters_all_ks3.mat`==

stores information of all the useful clusters from all acute sessions.

Each field is either:
1. Attribute of the cluster (sizes: N clusters x 1)
	- unique cluster id (mouse | session | probe | id, e.g. 23032 | 03 | 01 | 0247)
	- quality/template metrics (e.g. isi_violation_ratio, snr, etc.)
	- spike times (in cell arrays for each cluster)
	- depth/channel on the probe
	- which region it belongs to (eg. 'V1', 'MEC')
	- spatial information (eg. peak percentile of shuffle, odd even stability)
	- receptive field
2.  Behaviour/session information of the session
	- time vector
	- behaviour variables (time series, e.g. eye tracking, speed, position)
	- task relevant information (e.g. start/end time of each lap, reward time/location)

For individual sessions:
>==`/data/session_clusters.mat`==

### Preprocessing
See pipeline:
>https://github.com/SaleemLab/VR_NPX_analysis
### Spike Sorting
Pipeline built by Diao T. using spikeinterface + catGT
> https://github.com/SaleemLab/si_lab

It does following steps:
1. Preprocessing
2. Motion Correction
3. Kilosort3 + Kilosort 4
4. Compute Waveforms
5. Compute Merge Suggestions using UnitMatch
6. Merge Units
7. Compute metrics

Eventually files are stored in:
> `/mouse/ephys/date/acquisition/`
> Each of them have:
>  `~/probe0/sorters/kilosort3_merged/`
>  `~/probe0/waveform/kilosort3_merged/` 
>  `~/probe0_preprocessed/`
## Raw Data
### Ephys
The new neuropixel 2.0 acquisition has the format:
`/mouse/ephys/date/date_#acquisition_number#/`

The acute neuropixel 1.0 has:
`/mouse/ephys/date/`

Inside, you would have raw binary files and meta files of each probe.

### Bonsai
All other stimulus and behavioural tracking information are in:
`/mouse/bonsai/date/`
