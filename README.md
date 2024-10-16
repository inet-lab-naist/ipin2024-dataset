This is the dataset for the paper "Performance Evaluation of Fingerprint-Based Indoor Positioning Using RSSI in 802.11ah" presented at IPIN2024.

## Files
The correspondence between the datasets mentioned in the paper and the file names is as follows:

| Mention in Paper | File Name |
| - | - |
| Full dataset | `files/full_dataset.csv` |
| Small dataset | `files/small_dataset.csv` |

## Item Names
| Item Name | Description | Unit | 
|-|-|-| 
| index | Collection time (format: ISO 8601)| - |
| 11ac_ap** | RSSI from IEEE 802.11ac AP with id:** | - |
| 11ah_ap** | RSSI from IEEE 802.11ah AP with id:** | - |
| x | x-coordinate of the measured location | m |
| y | y-coordinate of the measured location | m |
| z | z-coordinate of the measured location | m |
| qw | Orientation at the time of measurement (quaternion qw) | - |
| qx | Orientation at the time of measurement (quaternion qx) | - |
| qy | Orientation at the time of measurement (quaternion qy) | - |
| qz | Orientation at the time of measurement (quaternion qz) | - |
| floor | Floor number within the building | - |
| measurement_point | ID to identify one measurement session. The same ID indicates the measurer continued walking. | - |
| room | ID to identify the room |
| block_x | x-coordinate with 1m precision (truncated) | m |
| block_y | y-coordinate with 1m precision (truncated) | m |
| block_z | z-coordinate with 1m precision (truncated) | m |

## Notes
- Information about which 11ah AP and 11ac AP were installed in proximity will be added later.
  