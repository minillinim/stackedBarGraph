# stackedBarGraph

## Overview

Code for making purdy stacked bar graphs. I really needed this one day so searching online for an answer I found only this question: https://stackoverflow.com/questions/19060144/more-efficient-matplotlib-stacked-bar-chart-how-to-calculate-bottom-values. So I wrote this. There is more stacked-bar-graph-esque goodness at the above link.


## Installation

Copy and paste at will

## Usage

The file contains one Class called 'StackedBarGrapher' which contains
one useful function called 'stackedBarPlot'.

Its required arguments are:

    ax                                  # pyplot axes to plot onto
    data                                # data to plot  --> A list of lists of FLOATS.
    cols                                # colors for each level in the stack

    Optional arguments:

    xLabels                     	# bar specific labels
    yTicks                        	# information used for making y ticks ["none", <int> or [[tick_pos1, tick_pos2, ... ],[tick_label_1, tick_label2, ...]]
    edgeCols                            # colors for edges
    showFirst                           # only plot the first <showFirst> bars
    scale                        	# scale bars to same height
    widths                        	# set widths for each bar
    heights                       	# set heights for each bar
    ylabel                              # label for x axis
    xlabel                              # label for y axis
    gap                                 # all a gap between the bars (use a float, default = 0. i.e. no gap)
    endGaps                             # allow gaps at end of bar chart (only used if gaps != 0.) True or False (default = False)

## Example usage 1

    from stackedBarGraph import StackedBarGrapher()
    SBG = StackedBarGrapher()
    SBG.demo()

## Example usage 2

    import numpy as np
    from matplotlib import pyplot as plt
    from stackedBarGraph import StackedBarGrapher
    SBG = StackedBarGrapher()

    d = np.array([[101.,0.,0.,0.,0.,0.,0.],
                  [92.,3.,0.,4.,5.,6.,0.],
                  [56.,7.,8.,9.,23.,4.,5.],
                  [81.,2.,4.,5.,32.,33.,4.],
                  [0.,45.,2.,3.,45.,67.,8.],
                  [99.,5.,0.,0.,0.,43.,56.]])

    d_widths = [.5,1.,3.,2.,1.,2.]
    d_labels = ["fred","julie","sam","peter","rob","baz"]
    d_colors = ['#2166ac', '#fee090', '#fdbb84', '#fc8d59', '#e34a33', '#b30000', '#777777']
    fig = plt.figure()

    ax = fig.add_subplot(111)
    SBG.stackedBarPlot(ax,
                       d,
                       d_colors,
                       xLabels=d_labels,
                       yTicks=7,
                       widths=d_widths,
                       scale=True
                      )
    plt.title("Scaled bars with set widths")

    fig.subplots_adjust(bottom=0.4)
    plt.tight_layout()
    plt.show()
    plt.close(fig)
    del fig

## Help

If you experience any problems using stackedBarGraph, open an [issue](https://github.com/minillinim/stackedBarGraph/issues) on GitHub and tell us about it.

## Licence and referencing

GPLv3 with love. Project home page, info on the source tree, documentation, issues and how to contribute, see http://github.com/minillinim/stackedBarGraph

## Copyright

Copyright (c) 2014 Michael Imelfort. See LICENSE.txt for further details.
