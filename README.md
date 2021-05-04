# Rate-Distortion Optimization with Spark + FFmpeg

Spark notebooks explore video rate-distortion optimization using content info.

## Intro
Streaming video efficiently relies on encoding at multiple resolution/bitrates to accomodate network conditions by switching adaptively.
<img src="https://smellslike.ml/img/adaptive_bitrate_streaming.png#center" width=800>

Video engineers search a grid of bitrate/resolution to maximize percieved quality using a metric like [VMAF](https://github.com/Netflix/vmaf) via Convex Hull optimization.

<img src="https://smellslike.ml/img/shot_level_optimization.png#center" width=800>

However, naive grid search is wasteful.

<img src="https://smellslike.ml/img/bitrate_ladder_1.png#center" width=800>

We are most interested in points near the Pareto Frontier.

<img src="https://smellslike.ml/img/bitrate_ladder_2.png#center" width=800>

## Getting Started
The notebooks in the ```notebooks/``` directory explore ideas from [Netflix](https://arxiv.org/pdf/2103.07564.pdf) to segment video at the shot-level and combining interpolation with content-based regression to reduce the search further. If you are using the Databricks platform, you can import the notebooks from these links:

* [Part I](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1969271421694072/827948633476116/5612335034456173/latest.html)
* [Part II](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1969271421694072/4057322776779238/5612335034456173/latest.html)
* [Part III](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1969271421694072/789288020732031/5612335034456173/latest.html)

### Requirements
* [Spark](https://spark.apache.org/)
* [pyspark](https://spark.apache.org/docs/latest/api/python/getting_started/install.html)
* [ffmpeg with VMAF](https://johnvansickle.com/ffmpeg/)
* [tensorflow>=2.0](https://www.tensorflow.org/)
* [rikai](https://github.com/eto-ai/rikai)


## Resources
* [Netflix Paper](https://arxiv.org/pdf/2103.07564.pdf)
* [Bitrate Optimization using Spark and FFmpeg](https://smellslike.ml/posts/bitrate-optimization-using-spark-and-ffmpeg/)
* [Toward A Practical Perceptual Video Quality Metric](https://netflixtechblog.com/toward-a-practical-perceptual-video-quality-metric-653f208b9652)
* [Introducing VMAF percentiles for video quality measurements](https://blog.twitter.com/engineering/en_us/topics/infrastructure/2020/introducing-vmaf-percentiles-for-video-quality-measurements.html)
