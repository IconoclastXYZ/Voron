# Results from Resonance Testing

## 20220507
### ABBN 30 head with PA6 CF hotend and Dragon HF

~/klipper/scripts/calibrate_shaper.py /tmp/resonances_x_*.csv -o /tmp/shaper_calibrate_x.png

Fitted shaper 'zv' frequency = 57.8 Hz (vibrations = 5.4%, smoothing ~= 0.053)
To avoid too much smoothing with 'zv', suggested max_accel <= 13000 mm/sec^2

Fitted shaper 'mzv' frequency = 58.8 Hz (vibrations = 0.0%, smoothing ~= 0.059)
To avoid too much smoothing with 'mzv', suggested max_accel <= 10200 mm/sec^2

Fitted shaper 'ei' frequency = 70.2 Hz (vibrations = 0.0%, smoothing ~= 0.065)
To avoid too much smoothing with 'ei', suggested max_accel <= 9200 mm/sec^2

Fitted shaper '2hump_ei' frequency = 87.6 Hz (vibrations = 0.0%, smoothing ~= 0.070)
To avoid too much smoothing with '2hump_ei', suggested max_accel <= 8500 mm/sec^2

Fitted shaper '3hump_ei' frequency = 105.0 Hz (vibrations = 0.0%, smoothing ~= 0.074)
To avoid too much smoothing with '3hump_ei', suggested max_accel <= 8100 mm/sec^2

Recommended shaper is mzv @ 58.8 Hz

~/klipper/scripts/calibrate_shaper.py /tmp/resonances_y_*.csv -o /tmp/shaper_calibrate_y.png

Fitted shaper 'zv' frequency = 40.6 Hz (vibrations = 1.9%, smoothing ~= 0.098)
To avoid too much smoothing with 'zv', suggested max_accel <= 6400 mm/sec^2

Fitted shaper 'mzv' frequency = 40.8 Hz (vibrations = 0.0%, smoothing ~= 0.122)
To avoid too much smoothing with 'mzv', suggested max_accel <= 4900 mm/sec^2

Fitted shaper 'ei' frequency = 49.2 Hz (vibrations = 0.0%, smoothing ~= 0.133)
To avoid too much smoothing with 'ei', suggested max_accel <= 4500 mm/sec^2

Fitted shaper '2hump_ei' frequency = 61.6 Hz (vibrations = 0.0%, smoothing ~= 0.142)
To avoid too much smoothing with '2hump_ei', suggested max_accel <= 4200 mm/sec^2

Fitted shaper '3hump_ei' frequency = 74.4 Hz (vibrations = 0.0%, smoothing ~= 0.148)
To avoid too much smoothing with '3hump_ei', suggested max_accel <= 4100 mm/sec^2

Recommended shaper is mzv @ 40.8 Hz
