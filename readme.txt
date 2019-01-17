
             High-Speed Tracking with Kernelized Correlation Filters

__________
Quickstart

1. Extract code somewhere.

2. The tracker is prepared to run on any of the 50 videos of the Visual Tracking
   Benchmark [3]. For that, it must know where they are/will be located. You can
   change the default location 'base_path' in 'download_videos.m' and 'run_tracker.m'.

3. If you don't have the videos already, run 'download_videos.m' (may take some time).

4. Execute 'run_tracker' without parameters to choose a video and test the KCF on it.


Note: The tracker uses the 'fhog'/'gradientMex' functions from Piotr's Toolbox.
Some pre-compiled MEX files are provided for convenience. If they do not work for your
system, just get the toolbox from http://vision.ucsd.edu/~pdollar/toolbox/doc/index.html


__________

The main interface function is 'run_tracker'. You can test several configurations (KCF,
DCF, MOSSE) by calling it with different commands:


 run_tracker
   Without any parameters, will ask you to choose a video, track using
   the Gaussian KCF on HOG, and show the results in an interactive
   figure. Press 'Esc' to stop the tracker early. You can navigate the
   video using the scrollbar at the bottom.

 run_tracker VIDEO
   Allows you to select a VIDEO by its name. 'all' will run all videos
   and show average statistics. 'choose' will select one interactively.

 run_tracker VIDEO KERNEL
   Choose a KERNEL. 'gaussian'/'polynomial' to run KCF, 'linear' for DCF.

 run_tracker VIDEO KERNEL FEATURE
   Choose a FEATURE type, either 'hog' or 'gray' (raw pixels).

 run_tracker(VIDEO, KERNEL, FEATURE, SHOW_VISUALIZATION, SHOW_PLOTS)
   Decide whether to show the scrollable figure, and the precision plot.

 Useful combinations:
 >> run_tracker choose gaussian hog  %Kernelized Correlation Filter (KCF)
 >> run_tracker choose linear hog    %Dual Correlation Filter (DCF)
 >> run_tracker choose gaussian gray %Single-channel KCF (ECCV'12 paper)
 >> run_tracker choose linear gray   %MOSSE filter (single channel)




