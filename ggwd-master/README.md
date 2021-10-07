## Generating the GW dataset

The scipts is cloned from https://github.com/timothygebhard/ggwd. The script is run in python2.7 and some changes needs to be made to run in python 3. 
The scripts in this repo are converted to python 3 by applying the following changes:


**1: generating_samples.py**

Line 69: 

*sys.stdout = os.fdopen(sys.stdout.fileno(), 'w', 0)*

->

*import io*

*sys.stdout = io.TextIOWrapper(open(sys.stdout.fileno(), 'wb', 0), write_through=True)*
      
     
**2.utils/samplegeneration.py**

Line 213:

*for key, value in waveform_params.iteritems():*

->

*for key, value in waveform_params.items():*   


**Run the code**

*python generate_sample.py --config-file=default.json*


**plot the output**

*python plot_sample.py --sample-id=0 --plot-path=./result.pdf*

this script needs to be debug
