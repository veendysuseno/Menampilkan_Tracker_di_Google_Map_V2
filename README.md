# GPS and SIM800L Project with Microcontroller Arduino Uno

This project uses a GPS module and a GSM SIM800L module to obtain location data and send it via SMS to a specific phone number.

## Description:

This code is designed to read location data (latitude and longitude) from the GPS module and then send the data in the form of a Google Maps link via SMS using the SIM800L module.

## Key Features:

- **GPS Module**: Retrieves real-time location data (latitude and longitude).
- **SIM800L GSM Module**: Sends location data obtained in the form of a Google Maps link to a predetermined telephone number via SMS.

## Required Components:

- Arduino (Uno, Mega, or other compatible models)
- GPS module (for example, Neo-6M)
- GSM SIM800L module
- Jumper cables

## Ways of working:

1. **Initialization**:
    - The SIM800L and Serial Monitor modules are initialized at a baud rate of 9600.
    - SIM800L module is set in text message mode (AT+CMGF=1).

2. **Main Loop**:
    - The program will check whether there is incoming data from the SIM800L module.
    - If there is incoming data, the program will check whether there is an "ON" command received via SMS.
    - If the "ON" command is received, the program will send an SMS message containing a Google Maps link with the current location.

3. **GPS Function**:
    - This function is used to read GPS data from Serial and convert it to latitude and longitude.
    - Google Maps links are created based on the latitude and longitude data obtained.

## How to Use:

1. Connect the GPS module and SIM800L to the Arduino according to the pin settings specified in the code.
2. Upload this code to Arduino.
3. Send an SMS in the appropriate format to the SIM800L module connected to the Arduino.
4. The module will send a Google Maps location link to the specified number if the command received is “ON”.

## Example of SMS

- To activate location sending, send an SMS with the content "ON" to the number connected to the SIM800L.

## Notes

- Make sure the telephone number entered in the code is correct.
- The GPS module takes several seconds to minutes to lock onto satellite signals and provide accurate location data.
