# RCWL-0516---Microwave-Radar-Sensor
RCWL-0516 4-28V 3mA Microwave Radar Sensor



Automation erstellenX:\automations\autom_tamota006.yaml
###
- alias: TASMOTA006 ON
  initial_state: true
  trigger: 
    - platform: state
      entity_id: binary_sensor.tasmota006_motion
      from: 'off'
      to: 'on'
  action:
    - service: light.turn_on
      data: 
        entity_id: light.flur
- alias: TASMOTA006 OFF
  initial_state: true
  trigger: 
    - platform: state
      entity_id: binary_sensor.tasmota006_motion
      from: 'on'
      to: 'off'
      for: '00:00:05'
  action:
    - service: light.turn_off
      data: 
        entity_id: light.flur 
