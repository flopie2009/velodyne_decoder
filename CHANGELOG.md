# Changelog

## [2.0.0] – 2021-11-11

### Added

- Support for PCAP file decoding with the `read_pcap()` function in Python and `StreamDecoder` in C++.
- More convenient data extraction from ROS bags with `read_bag()`.
- Standard calibration info provided by Velodyne is now used by default and `config.calibration_file` can be left unset
  in most cases.
- `TIMINGS_AVAILABLE` was added for details about which models support point timing info. The current list is:
  `['HDL-32E', 'VLP-16', 'VLP-32C', 'VLS-128']`.

### Changed

- The decoded scans are now returned as a contiguous float32 NumPy arrays instead of PCL-compatible structs by default.
  You can pass `as_pcl_structs=True` to the decoding functions for the old behavior.
- Model ID naming scheme has been updated to better match the typical forms used by Velodyne. <br>
  Before: `['VLP16', '32C', '32E', 'VLS128']`. <br>
  After: `['HDL-32E', 'HDL-64E', 'HDL-64E_S2', 'HDL-64E_S3', 'VLP-16', 'VLP-32C', 'VLS-128']`.
- Conversion to NumPy arrays is now done without any unnecessary data copying.

### Fixed

- Fixed a Python 2 ROS message decoding error.

## [1.0.1] – 2021-05-19

Initial release.

[2.0.0]: https://github.com/valgur/velodyne_decoder/compare/v1.0.1...v2.0.0

[1.0.1]: https://github.com/valgur/velodyne_decoder/releases/tag/v1.0.1