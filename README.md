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

`pbs_feat <subject-list> <epi> <maskdir> <tr> [options]`

##Cumpulsory Arguments

- _subject-list_ - file containing list of subject IDs and subject
  directories in the form of 'subject-000
  /Data/Project-000/subject-000'

- _epi_ - filename of epi (which is inside subject directory)

- _maskdir_ - directory containing individual region masks

- _tr_ - tr from scanner protocol (in seconds)

##Optional Arguments

- _i_: initial structural image to register epi to before registering
  to template

- _h_: highpass cuttoff (if not provided, no temporal filtering will
  be performed)

- _s_: smoothing parameter (if not provided, no smoothing will be
  performed)

- _t_: feat template file (if not provided, default will be used)

##Output

In each subject directory, the following output will be created:

- _subject-id_.feat

- template.fsf

- timeseries.txt
