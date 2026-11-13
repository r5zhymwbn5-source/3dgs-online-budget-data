# Multi-scene and multi-seed experiment metrics

These CSV files are a point-in-time export of the 1M-ceiling and 2M-ceiling follow-ups, without local file paths. Consult the status and validation fields for completion.

`per_run_metrics.csv` retains the status of every planned scene/seed/method combination. `highcap_full_per_run.csv` and `highcap_diagnostic.csv` contain the separate 2M-ceiling follow-up. `forecast_1m_diagnostic.csv` records forecast/reference pairs and censoring; its difference is blank if either side is capped. `per_view_metrics.csv` contains metrics for completed renders; render indices refer to the common held-out ordering. Empty LPIPS values mean that scoring is not complete. A reference is censored whenever `censored_events` is greater than zero.

All images are reduced-resolution; indoor images were derived locally from the available Mip-NeRF 360 images. Taming and DashGaussian have different training implementations and adapted schedules. Concurrent runtimes are intentionally excluded. The 2M diagnostic uses a different reference trainer and changes the provisional schedule as well as the ceiling.

No images, model files, source code, pretrained weights or local paths are included here. The original public dataset is available from the [Mip-NeRF 360 dataset page](https://jonbarron.info/mipnerf360/). This numerical export alone does not fully reproduce the experiments.
