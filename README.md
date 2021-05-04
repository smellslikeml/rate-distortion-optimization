# Rate-Distortion Optimization with Spark + FFmpeg

Spark notebooks explore video rate-distortion optimization using content info.

Resources:
* [Netflix Paper](https://arxiv.org/pdf/2103.07564.pdf)
* [Bitrate Optimization using Spark and FFmpeg](https://smellslike.ml/posts/bitrate-optimization-using-spark-and-ffmpeg/)
* [Toward A Practical Perceptual Video Quality Metric](https://netflixtechblog.com/toward-a-practical-perceptual-video-quality-metric-653f208b9652)
* [Introducing VMAF percentiles for video quality measurements](https://blog.twitter.com/engineering/en_us/topics/infrastructure/2020/introducing-vmaf-percentiles-for-video-quality-measurements.html)

Efficient video streaming relies on adaptive bitrates
![ABR](https://smellslike.ml/img/adaptive_bitrate_streaming.png#center)

Video engineers use grid search to optimize percieved quality subject to constrains on bitrate/resolution.

![RD-curve](https://smellslike.ml/img/shot_level_optimization.png#center)

But a naive search can be wasteful

![naive search](https://smellslike.ml/img/bitrate_ladder_1.png#center)

When we are really interested in points near the Pareto Frontier

![PF](https://smellslike.ml/img/bitrate_ladder_2.png#center)

These notebooks explore ideas from [Netflix](https://arxiv.org/pdf/2103.07564.pdf) to segment video at the shot-level and combining interpolation with content-based regression to reduce the search further.
