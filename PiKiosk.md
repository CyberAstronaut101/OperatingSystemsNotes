# Setting up raspberry pi zero w to run on HDMI kiosk mode


```bash
# Get Monitor Details

# create binary edid dump
# ! DONT Cat the binary !
$ tvservice -d /tmp/edid_info

$ edidparser /tmp/edid_info

# Looking for "preferred mode remained as..."
`200~HDMI:EDID preferred mode remained as CEA (83) 1920x1080p @ 60 Hz with pixel clock 148 MHz`

# Edit /boot/config.txt

    # Always force HDMI display over DVI
    hdmi_group=2
    # HDMI mode as reported by the display in edid dump above
    hdmi_mode=83


sudo apt install xinit xorg
```
