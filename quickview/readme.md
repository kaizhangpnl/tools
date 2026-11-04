## Quickview on Chrysalis  

## Use shared installation 

```
$ module load miniforge3/25.3.1 
$ conda activate /lcrc/group/e3sm/share/quickview
```

## Running Quickview 

Type 

```
$ quickview
```

You will see 

```
Loading plugin :  /lcrc/group/e3sm/share/quickview/lib/python3.14/site-packages/e3sm_quickview/plugins/eam_gridlines.py
Loading plugin :  /lcrc/group/e3sm/share/quickview/lib/python3.14/site-packages/e3sm_quickview/plugins/eam_projection.py
Loading plugin :  /lcrc/group/e3sm/share/quickview/lib/python3.14/site-packages/e3sm_quickview/plugins/eam_reader.py
Loading plugin :  /lcrc/group/e3sm/share/quickview/lib/python3.14/site-packages/e3sm_quickview/plugins/eam_filters.py
connect /var/run/com.apple.launchd.2Rr5ZlkMQN/org.xquartz:0: Connection refused
tauri-server-port=42757

Use URL below to connect to the application:

  => http://localhost:42757/

```

Note that the port number (here 42747) will be changed each time. 

Don't close this tab. Open a new tab and login to Chrysalis this way:  

```
ssh -N -L 42757:localhost:42757 YOURUSERNAME@chrysalis.lcrc.anl.gov 
```

Then login the system. Don't close the tab. 

Now open a browser on your local machine and copy/paste the following as the address: 

```
http://localhost:42757/
```

Then you will be able to see the Quickview interface. 

## Connectivity files 

The connectivity files are located at 

```
/lcrc/group/e3sm/share/connectivity
```

You can create a soft link of the connectivity file in the simulation directory, so that you can locate it more easily in Quickview. For example, 

```
ln -s /lcrc/group/e3sm/share/connectivity/connectivity_ne30pg2_TEMPEST.scrip.nc /path/to/simulation 
```


## Installation history 

```
$ conda create --prefix /lcrc/group/e3sm/share/quickview -c conda-forge python=3.14 typing_extensions e3sm-quickview mesalib -y
$ conda activate /lcrc/group/e3sm/share/quickview 
$ conda install e3sm_compareview 
```


## Install your own 

```
$ module load miniforge3/25.3.1
$ conda create -n quickview -c conda-forge python=3.14 typing_extensions e3sm-quickview mesalib -y
$ conda install e3sm_compareview # if you need it 
$ conda activate quickview
```

/lcrc/group/e3sm/share/connectivity
