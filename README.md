# ESP32-C3 Super Mini KiCad Schematic

An ESP32-C3 Super Mini KiCad Schematic based on the AliExpress ESP32-C3 Super Mini boards, with the following improvements over the original design.

## Improvements

### Antenna — Major Improvement

| | Original | This Design |
|---|---|---|
| **Part** | CrossAir CA-C03 | Johanson 2450AT18A100 |
| **Frequency** | 2.7 GHz (mistuned for 2.4 GHz use) | 2.4 GHz (properly tuned) |
| **Matching Network** | None | Full T-network |
| **Placement** | Poorly placed | Optimised |

The original design used a **CrossAir CA-C03** antenna — a 2.7 GHz antenna pressed into service at 2.4 GHz with no matching network. The result is a mistuned antenna with poor radiation efficiency.

This design replaces it with a **Johanson 2450AT18A100**, a proper 2.4 GHz chip antenna, paired with a full T-network matching circuit using Murata 0201 RF components:

```
RF feed → 2.7 nH (series) → 1.0 pF (shunt to GND) → 3.9 nH (series) → Antenna
```

This ensures the antenna is correctly matched to 50 Ω at 2.4 GHz, maximising radiated power and receiver sensitivity for Wi-Fi and Bluetooth operation.

## License

This work is licensed under a [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

[![CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

You are free to share and adapt this material for any purpose, provided appropriate credit is given.
