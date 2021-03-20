## Execution Time Performance (CPU)
|  Networks     | Data-Load | Compile |   Train   |   Test  |   Total   |
| :------:      | :-------: | :-----: | :------:  | :-----: | :------:  |
| **MLP**       |  0.438s	  | 0.124s	| 68.099s   | 0.885s  | 69.546s   |
| **CNN**       |  0.412s	  | 0.018s	| 1187.64s  | 5.025s	| 1193.095s |
| **RNN**       |  0.607s	  | 0.944s	| 124.32s	  | 6.728s	| 132.599s  |
| **LSTM**      |  0.62s	  | 1.523s	| 373.997s	| 21.902s	| 398.042s  |
|**Autoencoder**|  0.521s	  | 0.875s	| 146.194s	| 6.035s	| 153.625s  |

## Execution Time Performance (GPU)
|  Networks     | Data-Load | Compile |   Train   |   Test  |   Total   |
| :------:      | :-------: | :-----: | :------:  | :-----: | :------:  |
| **MLP**       |  0.608s	  | 0.111s	| 11.099s   | 0.349s  | 12.167s   |
| **CNN**       |  0.577s	  | 0.013s	| 67.221s   | 0.596s	| 68.407s   |
| **RNN**       |  0.455s	  | 5.706s	| 42.82s	  | 1.067s	| 50.048s   |
| **LSTM**      |  0.404s	  | 6.225s	| 41.686s	  | 1.446s	| 49.761s   |
|**Autoencoder**|  0.296s	  | 5.686s	| 12s	      | 1.292s	| 19.274s   |

## Execution Time Performance (TPU)
|  Networks     | Data-Load | Compile |   Train   |   Test  |   Total   |
| :------:      | :-------: | :-----: | :------:  | :-----: | :------:  |
| **MLP**       |  0.361s	  | 0.012s	| 45.546s   | 1.425s  | 47.344s   |
| **CNN**       |  0.597s	  | 0.022s	| 123.921s  | 1.556s	| 126.096s  |
| **RNN**       |  0.351s	  | 0.335s	| 41.394s	  | 3.937s	| 46.017s   |
| **LSTM**      |  0.572s	  | 1.304s	| 112.691s  | 10.036s	| 124.603s  |
|**Autoencoder**|  0.355s	  | 0.563s	| 38.689s   | 2.28s	  | 41.887s   |

## Execution Time Performance (All Hardware Totals)
|  Networks     | Data-Load | Compile |   Train   |
| :------:      | :-------: | :-----: | :------:  | 
| **MLP**       |  69.546s  | 12.167s	| 47.344s   |
| **CNN**       |  1193.095s| 68.407s	| 126.096s  |
| **RNN**       |  132.599s	| 50.048s	| 46.017s	  |
| **LSTM**      |  398.042s | 49.761s	| 124.603s  |
|**Autoencoder**|  153.625s	| 19.274s	| 41.887s   |
