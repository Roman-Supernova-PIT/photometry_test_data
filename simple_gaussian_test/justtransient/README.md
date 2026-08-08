Images in this directory where created by an early version of snappl.image_simulator.

These images contain no stars, but a single transient.  All were created using a PSF:
```
   GaussianPSF( sigmax=1., sigmay=1., theta=0. )
```

Images cover MJD 60000 through 60060, every 5 days.

There is a transient at `RA=128., Dec=42.` It starts at MJD 60010,
rises linearly in flux from zero to peak magntude 21. at MJD 60030.,
then declines linearly to zero at MJD 60060.

Each subdirectory has a different combination of various settings used to stress test photometry algrorithms. They are:

noiseless:
These images are perfectly aligned and noiseless.

justsky:
These images are perfectly aligned and were given a sky noise with an RMS of 30 counts

justpoisson:
These images are perfectly aligned and were given poisson noise.

bothnoise:
These images are perfectly aligned and recieved both sky noise with an RMS of 30 and poisson noise.

shifted_noiseless:
The same as noiseless, but the images are shifted and rotated, the angles and image centers used are listed below:

`--image-centers 128.      42.     127.999   42.     128.001   42.     128.      41.999  127.999   41.999`
`  128.001   41.999  128.      42.001  127.999   42.001  128.001   42.001  128.      42.0005 127.999   42.0005 128.001`
`   42.0005 128.      42.     -θ   0.  30.  60.  90. 120. 150. 180. 210. 240. 270. 300. 330. 360. `

I.e. the image centers are shifted in x by 0.001, -0.001, and 0.0 degrees, and shifted in y by 0.001, -0.001, 0.0, and
0.0005 degrees. Every combination of these shifts was taken to arrive at 12 unique centers, and then an additional
image at the original 128, 42 center was added to get to the 13 images to match the other subdirectories.

The angles are uniformly spaced between 0 and 360 degrees, seperated by 30 degrees each.

13 images were chosen to make sure that photometric algorithms hold up under supernaturally unlucky conditions.

shifted_poisson:
See above, plus poisson noise.
