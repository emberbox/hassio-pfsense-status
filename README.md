# hassio-pfsense-status

https://github.com/ndejong/pfsense_fauxapi#api-action-summary


- platform: pfsense_status
  host: 192.168.1.1
  name: pfSense status
  apikey: !secret pfsense_status_apikey
  apisecret: !secret pfsense_status_apisecret


#-- pfSense -----
#this will call the python script and store the cpu temp information in a sensor. the script will export
#the rest of the data into a file. we cant dump all of the data into 1 sensor since there is a 255 character
#limit for the sensor.

# - platform: command_line
#   command: "python3 custom_components/pfsense/pffa_get_system_stats.py 192.168.1.1 apikey apisecret"

# - platform: file
#   file_path: /tmp/pfSense_stats.json
#   name: pfSense_CPU_temp
#   value_template: '{{ value_json["data"]["stats"]["temp"] }}'
#   unit_of_measurement: "°C"

# - platform: file
#   file_path: /tmp/pfSense_stats.json
#   name: pfSense_uptime
#   value_template: '{{ value_json["data"]["stats"]["uptime"] }}'

# - platform: file
#   file_path: /tmp/pfSense_stats.json
#   name: pfSense_mem
#   value_template: '{{ value_json["data"]["stats"]["mem"] }}'
#   unit_of_measurement: "%"

# - platform: file
#   file_path: /tmp/pfSense_stats.json
#   name: pfSense_cpu
#   value_template: '{{ ( ( ((value_json["data"]["stats"]["cpu"].split("|")[0] | float) / (value_json["data"]["stats"]["cpu"].split("|")[1] | float)) - 1.0 ) * 100.0 ) | round(1) }}'
#   unit_of_measurement: "%"

# - platform: file
#   file_path: /tmp/pfSense_stats.json
#   name: pfSense_mbufpercent
#   value_template: '{{ value_json["data"]["stats"]["mbufpercent"] }}'
#   unit_of_measurement: "%"

# - platform: file
#   file_path: /tmp/pfSense_stats.json
#   name: pfSense
