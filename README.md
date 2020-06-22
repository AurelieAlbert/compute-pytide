# Filtering eNATL60-BLBT02 surface fields to get rid of coherent tide with the CNES pytide tool

## First tests with demo FES time serie

  - reproducing analysis from [pytide package](https://github.com/CNES/pangeo-pytide/blob/master/README.md), on mac : https://github.com/AurelieAlbert/compute-pytide/blob/master/2020-04-28-AA-test-pytide-fes-time-series-mac.ipynb
  - same analysis with h as a dataarray and some spectrum computed : https://github.com/AurelieAlbert/compute-pytide/blob/master/2020-04-28-AA-test-pytide-fes-time-series-xarray-spectrum-mac.ipynb
  - on occigen, conda pytide environment prepacked on cal1, same tests : https://github.com/AurelieAlbert/compute-pytide/blob/master/2020-04-29-AA-test-pytide-fes-time-series-xarray-spectrum-occigen.ipynb
  
## Tests on eNATL60 ssh data on hal, full batch nodes, 40 workers asked, 8-12h

  - tidal analysis + save the amplitude and phase + save the ssh-tide timestep by timestep 
    - for [1 month](https://github.com/AurelieAlbert/compute-pytide/blob/master/2020-05-04-AA-timing-pytide-eNATL60-BLBT02-ssh-hal-dask-future-1month-batch-full-nodes-queue.ipynb)
    - for [3 months](https://github.com/AurelieAlbert/compute-pytide/blob/master/2020-05-04-AA-timing-pytide-eNATL60-BLBT02-ssh-hal-dask-future-3month-batch-full-nodes-queue.ipynb)
    - for [6 months](https://github.com/AurelieAlbert/compute-pytide/blob/master/2020-05-05-AA-timing-pytide-eNATL60-BLBT02-ssh-hal-dask-future-6month-batch-full-nodes-queue.ipynb)
    - for [12 months half of the domain](https://github.com/AurelieAlbert/compute-pytide/blob/master/2020-05-06-AA-timing-pytide-eNATL60-BLBT02-ssh-hal-dask-future-12month-batch-full-nodes-queue-midomainX1.ipynb)
    - for 12 months full domain ? crashed
    
  - difficult to time with interactive session closing regularly, 3 month = 26mn, 1 year 1/2 domain = >2h
  
## Final computation half the domain at the time, writing the output in hourly files
  
   - first half : https://github.com/AurelieAlbert/compute-pytide/blob/master/2020-05-11-AA-launch-pytide-eNATL60-BLBT02-ssh-12month-midomainX1-on-hal.ipynb
   - second half : https://github.com/AurelieAlbert/compute-pytide/blob/master/2020-05-11-AA-launch-pytide-eNATL60-BLBT02-ssh-12month-midomainX2-on-hal.ipynb
   - recombination of harmonic analysis : https://github.com/AurelieAlbert/compute-pytide/blob/master/2020-05-15-AA-recombine-along-x-amp-phase-results-from-pytide.ipynb and of the filtered ssh : https://github.com/AurelieAlbert/compute-pytide/blob/master/2020-05-19-AA-recombine-tide-results-from-pytide-switch-axis-when-needed.ipynb
   - adding a time_counter dimension in all files :
   
## Comparison of harmonic analysis with results from tidal-tools

 - plots : https://github.com/AurelieAlbert/compute-pytide/blob/master/maps_amp_phi_M2-S2-N2-O1-K1_eNATL60_tidal-tools-pytide.png
 
## Assessing the filtering of tidal signal

  - time series and spectrum in one point of the domain
