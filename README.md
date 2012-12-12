PBS FEAT
==========

A collection of scripts designed to perform first level processing on
fMRI data on a cluster employing a PBS job scheduler.

This script launches a PBS job for each subject that will perform the
desired preprocessing and extract a time series for a given atlas. To
do so, this script relies on feat as well as additional utilties
provided in the FSL package.

# Installation #

- Clone the git repository

`git clone http://github.com/tnez/pbs-feat.git`

- Run the following script which will add the appropriate paths to
your bashrc file.

`./pbs-feat/setup.sh`

# Usage #

##Example

`pbs-feat subject-list.txt NIfTI/rest.nii atlas/aal.nii.gz --smooth-dim=5.0`

##Input

- subject-list - file containing list of subject IDs and subject
  directories in the form of 'subject-000
  /Data/Project-000/subject-000'

- epi - filename of epi (which is inside subject directory)

- atlas - integer labeled atlas (must be in MNI space)

- fieldmap (optional) - filename of fieldmap (which is inside subject
  directory)

- mag (optional) - filename of magnitude image (which is inside
  subject directory)

- smooth-dim (optional) - smoothing parameter

- hp-cut (optional) - highpass cuttoff

##Output

In each subject directory, the following output will be created:

- _epi-basename_-mc.nii.gz
- mc-params.csv
- _subject-id_.feat
- template.fsf
- timeseries.csv
