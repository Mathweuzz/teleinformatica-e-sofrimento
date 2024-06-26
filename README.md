## Fuel Tank Monitoring System

This project is a web application for monitoring fuel levels in tanks, incorporating data received from Arduino sensors through a serial port.

**Key features:**

* **Data collection:** Reads fuel level data from Arduino sensors connected via serial port.
* **Data storage:** Stores data in an SQLite database, including timestamp, fuel level, and tank ID.
* **Web interface:** Provides a user-friendly dashboard for visualizing fuel levels, filtering data by tank and date range, and viewing statistics.
* **Real-time updates:** Utilizes SocketIO for real-time data updates on the web interface.

**Project structure:**

* **`app.py`:** Flask application that handles data processing, database interaction, and web server functionality.
* **`serial_port_reader.py`:** Python script that reads data from the serial port and sends it to the Flask server.
* **`index.html`:** HTML template for the web dashboard.
* **`dashboard.js`:** JavaScript code for handling data visualization, interactions, and SocketIO communication.
* **`style.css`:** CSS stylesheet for the web dashboard.
* **`lora_codes/`:** Folder containing Arduino code for transmitter and receiver using LoRa modules (optional).

**Getting started:**

1. **Install dependencies:** Install the required libraries by running `pip install -r requirements.txt`.
2. **Configure serial port:** Modify the `arduino = serial.Serial('/dev/ttyACM0', 9600)` line in `serial_port_reader.py` to match your Arduino's serial port and baud rate.
3. **Connect Arduino:** Connect the Arduino sensors to the computer's serial port.
4. **Start the server:** Run `python3 app.py` to start the Flask server.
5. **Access the dashboard:** Open the URL `http://localhost:5000/` in your web browser to access the dashboard.
6. **Send data (optional):**
    * Upload the Arduino code in the `lora_codes` folder to your transmitter and receiver devices.
    * Run `python3 serial_port_reader.py` to start collecting and sending data.

**Additional information:**

* The database is created automatically when the Flask application starts.
* The `lora_codes` folder contains Arduino code for transmitter and receiver using LoRa modules, which can be used for wireless communication over longer distances.

This project provides a full framework for monitoring fuel levels in tanks. You can further extend it by adding features like:

* **Alert notifications:** Send email or SMS notifications when fuel levels reach certain thresholds.

* **Historical data analysis:** Implement charting libraries to display historical trends and patterns in fuel level data.
