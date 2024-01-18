# Fitting code for PhiTauTau

## Setup

Follow the setup instructions for combine with CMSSW_10_2_13.
Install `rhalphalib` locally (there may be some modifications necessary, things don't always play nice by default).
Clone this repo into `CMSSW_10_2_13/src/`.

### To install rhalphalib:

1. Install rhalphalib
   git checkout -b phitautau origin/phitautau
2. In CMSSW_10_2_13
   scram b
   pip install flake8 --user
   pip install --user https://github.com/drankincms/rhalphalib/archive/master.zip

## Running

`runLimits.sh` is the top script, which will call the other scripts in this directory as needed. An example invocation is below:
```
./runLimits.sh Dec12_2017/34 full200 hadel hadmu hadhad
```

## Local scripts

While the fitting is expected to run remotely, the plotting etc can easily be run locally. The scripts to copy down the necessary files are in `local_scripts/`. A standard invocation is below:
```
./plotPhi.sh Dec12_2017 34 2017
```


# Andrzej Running

```
cd datacards/
python3 make_cards.py --hist ~/work/tauana/drankin_Nov30_2017_UL/hists_sum_ --year 2017 --cat hadmu --cat hadel --cat hadhad --tag Nov13_2017_UL/1
cd ..
./runLimits.sh Nov13_2017_UL/1 full200 hadmu hadel hadhad
```