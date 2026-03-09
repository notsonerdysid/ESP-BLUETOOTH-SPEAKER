## ESP-BLUETOOTH-SPEAKER  
I used esp's bluetooth feature with a speaker and a audio amplifer to create. DIY bluetooth speaker.   

**COMPONENTS:**  
1. ESP32
2. 4 OHM SPEAKER
3. MAX98357A AUDIO AMPLIFIER
4. 3.7V BATTERY  

Here's the schematics:  
<img width="954" height="490" alt="Screenshot 2026-03-09 104459" src="https://github.com/user-attachments/assets/de3c441f-1579-48db-8038-bb4639502500" />  

**Code:**  

    #include "AudioTools.h"
    #include "BluetoothA2DPSink.h"

    I2SStream i2s;
    BluetoothA2DPSink a2dp_sink(i2s);

    void setup() 
    {
        auto cfg = i2s.defaultConfig();
        cfg.pin_bck = 27;
        cfg.pin_ws = 26;
        cfg.pin_data = 25;
        i2s.begin(cfg);

        a2dp_sink.start("COOL_ESP_SPEAKER");
    }

    void loop() 
    {
        // no code here
    }

