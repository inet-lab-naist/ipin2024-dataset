# Dataset for Indoor Positioning Using IEEE 802.11ac and 802.11ah (IPIN 2024)

This is the dataset for the paper "[Performance Evaluation of Fingerprint-Based Indoor Positioning Using RSSI in 802.11ah](https://ieeexplore.ieee.org/document/10786180)" presented at [IPIN 2024](https://ipin-conference.org/2024/).

T. Matsunaga, I. Arai, Y. Atarashi, A. Endo and K. Fujikawa, "Performance Evaluation of Fingerprint-Based Indoor Positioning Using RSSI in 802.11ah," 2024 14th International Conference on Indoor Positioning and Indoor Navigation (IPIN), Kowloon, Hong Kong, 2024, pp. 1-7, doi: 10.1109/IPIN62893.2024.10786180.

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
| 11ac_ap**_rssi | RSSI, Receive the beacon frame sent from the installed AP with ID:** to the receiver of the measurer. | - |
| 11ah_receiver_**_rssi | RSSI, Receive the beacon frame sent from a measurer's 11ah AP to the installed 11ah receiver with ID:** | - |
| x | x-coorof the measured location | m |
| y | y-coordinate of the measured location | m |
| z | z-coordinate of the measured location | m |
| qw | Orientation at the time of measurement (quaternion qw) | - |
| qx | Orientation at the time of measurement (quaternion qx) | - |
| qy | Orientation at the time of measurement (quaternion qy) | - |
| qz | Orientation at the time of measurement (quaternion qz) | - |
| floor | Floor number within the building | - |
| measurement_point | ID to identify one measurement session. The same ID indicates the measurer continued walking. | - |
| room | ID to identify the room | |
| block_x | x-coordinate with 1m precision (truncated) | m |
| block_y | y-coordinate with 1m precision (truncated) | m |
| block_z | z-coordinate with 1m precision (truncated) | m |

## Mapping of 11ac APs and 11ah receivers that were geographically close to each other

| 11ac | 11ah |
| - | - |
| `11ah_receiver_02_rssi` | `11ac_ap21_rssi` |
| `11ah_receiver_03_rssi` | `11ac_ap27_rssi` |
| `11ah_receiver_04_rssi` | `11ac_ap18_rssi` |
| `11ah_receiver_05_rssi` | `11ac_ap26_rssi` |
| `11ah_receiver_06_rssi` | `11ac_ap28_rssi` |
| `11ah_receiver_07_rssi` | `11ac_ap14_rssi` |
| `11ah_receiver_08_rssi` | `11ac_ap29_rssi` |
| `11ah_receiver_09_rssi` | `11ac_ap05_rssi` |
| `11ah_receiver_10_rssi` | `11ac_ap19_rssi` |
| `11ah_receiver_11_rssi` | `11ac_ap22_rssi` |
| `11ah_receiver_12_rssi` | `11ac_ap16_rssi` |
| `11ah_receiver_13_rssi` | `11ac_ap08_rssi` |
| `11ah_receiver_14_rssi` | `11ac_ap17_rssi` |
| `11ah_receiver_15_rssi` | `11ac_ap09_rssi` |
| `11ah_receiver_16_rssi` | `11ac_ap10_rssi` |
| `11ah_receiver_17_rssi` | `11ac_ap12_rssi` |
| `11ah_receiver_18_rssi` | `11ac_ap13_rssi` |
| `11ah_receiver_19_rssi` | `11ac_ap20_rssi` |
| `11ah_receiver_20_rssi` | `11ac_ap07_rssi` |
| `11ah_receiver_21_rssi` | `11ac_ap15_rssi` |
| `11ah_receiver_22_rssi` | `11ac_ap23_rssi` |
| `11ah_receiver_23_rssi` | `11ac_ap11_rssi` |

## Correction Notice

After the publication of the paper, we discovered an error in the data and would like to provide a correction. We intended to use the RSSI values of 23 geographically proximate pairs of 11ac APs and 11ah receivers as features; however, due to a mistake in the dataset construction program, one pair was included in the dataset despite not being geographically close. In addition to the features listed in the table titled `Mapping of 11ac APs and 11ah receivers that were geographically close to each other`, we were also experimenting with `11ah_receiver_01_rssi` and `11ac_ap25_rssi`, but these two values are not geographically proximate. Therefore, the results of the paper were based on an incomplete dataset where 22 pairs were close, but one pair was not close.

When conducting experiments using the correct 22 pairs, the results are as follows:

- **Area Classification (Inside/Outside Furnace Room) Accuracy**
  - Number of 11ac APs with highest F1 Score: 19 → 18
- **Area Classification (Room) Accuracy**
  - Highest F1 Score: 0.997 → 0.995
  - Number of 11ah receivers with highest F1 Score: 20 → 18
- **ECDF**
  - **11ac**
    - Probability of positioning error less than 10m (%): 99.6 → 99.5
  - **11ah**
    - Probability of positioning error less than 10m (%): 97.4 → 97.0
- **Positioning Error (MedAE)**
  - **11ac**
    - Lowest MedAE: 2.537 → 2.564
    - Number of APs with lowest MedAE: 21 → 19
  - **11ah**
    - Lowest MedAE: 3.722 → 3.745
    - Number of Receivers with lowest MedAE: 22 → 20
