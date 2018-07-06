---
layout: post
title:  "RaspberryPi Sprinkler Hijinx"
date:   2018-07-05 19:00:01 -0500
categories: blog 
tags: [python, homeautomation, raspberrypi]
---

# The Problem
My sprinkler system is pretty dumb.  I'm having to constantly remember to turn it off when there is rain in the forecast.  There is the ability to toggle it off in the event of moisture detected.  However this provides no 'smart' ability to be able to turn off when the percentage of rain chance in the future is high, but the sensor is currently dry.

# The Solution
1. RaspberryPi - this is good to control things, plus runs Python natively with GPIO control.
2. Relay board - this is a mountable board on the RaspberryPi, and can connect directly into my Sprinkler Control panel (in the sensor inputs).
3. Weather Underground API - this is a good API to get percentage of precipitation for a given area.
4. Cron Job - run the forecast job every hour, if the percentage over the next few "time blocks" is over X percentage, send a signal to the relay to open the switch on the Sprinkler panel.
