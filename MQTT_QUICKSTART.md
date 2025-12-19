# MQTT Quick Start

## Step 1: Enable MQTT in Configuration

1. Locate your config file:
   - **Windows:** `%USERPROFILE%\.edcopter2.0\config.json`
   - **Path example:** `C:\Users\YourName\.edcopter2.0\config.json`

2. Edit the file (create it if it doesn't exist) and add:

```json
{
  "ipAddress": "0.0.0.0",
  "edcopilotIp": "127.0.0.1",
  "port": 4500,
  "debug": false,
  "mqtt": {
    "enabled": true,
    "brokerUrl": "mqtt://homeassistant.local:1883",
    "username": "",
    "password": "",
    "baseTopic": "edcopter"
  }
}
```

3. **Customize for your setup:**
   - Replace `homeassistant.local` with your Home Assistant IP (e.g., `192.168.1.100`)
   - Add your MQTT username/password if required
   - Change `baseTopic` if you want a different topic prefix

## Step 2: Find Your Home Assistant IP

### Option A: Check Home Assistant Web Interface
1. Open Home Assistant
2. Go to **Settings** → **System** → **Network**
3. Look for your IP address (e.g., `192.168.1.100`)

### Option B: Use command line
```bash
ping homeassistant.local
```

## Step 3: Get Your MQTT Credentials

1. In Home Assistant, go to **Settings** → **Add-ons**
2. Open **Mosquitto broker**
3. Create a user in **Configuration** tab if needed
4. Note down username and password

## Step 4: Start EDCoPTER

Run EDCoPTER normally. You should see in the console:

```
Connecting to MQTT broker: mqtt://192.168.1.100:1883
✅ MQTT connected successfully!
📡 Published test message to edcopter/status
```

## Step 5: Verify in Home Assistant

### Using MQTT Integration Page
1. Go to **Settings** → **Devices & Services** → **MQTT**
2. Click **Configure**
3. Click **Listen to a topic**
4. Enter: `edcopter/#`

### Using Developer Tools
1. Go to **Developer Tools** → **MQTT**
2. In the "Listen to a topic" section, enter: `edcopter/status`
3. Click **Start Listening**

## Troubleshooting

### "MQTT connection error: getaddrinfo ENOTFOUND"
- ❌ Problem: Can't resolve hostname
- ✅ Solution: Use IP address instead: `mqtt://192.168.1.100:1883`

### "MQTT connection error: connect ECONNREFUSED"
- ❌ Problem: Mosquitto broker not running or wrong port
- ✅ Solution: 
  - Check Mosquitto add-on is started in Home Assistant
  - Verify port is 1883 (default)

### "MQTT connection error: Connection refused: Not authorized"
- ❌ Problem: Wrong username/password
- ✅ Solution: Double-check credentials in config.json

### No connection messages appear
- ❌ Problem: MQTT not enabled or config not loaded
- ✅ Solution:
  - Verify `"enabled": true` in config.json
  - Try setting `"debug": true` to see more logs
  - Restart EDCoPTER

## Example Working Config

```json
{
  "ipAddress": "0.0.0.0",
  "edcopilotIp": "127.0.0.1",
  "port": 4500,
  "debug": true,
  "mqtt": {
    "enabled": true,
    "brokerUrl": "mqtt://192.168.1.100:1883",
    "username": "mqtt_user",
    "password": "secure_password",
    "baseTopic": "edcopter"
  }
}
```

## Next Steps

Once you see the test message successfully published:

1. **Monitor topics** - Subscribe to `edcopter/#` to see all messages
2. **Create sensors** - Add Home Assistant sensors to display the data
3. **Future features** - Watch for updates that will broadcast game events:
   - Location changes
   - Combat events
   - Ship status
   - Control states (landing gear, hardpoints, etc.)

## Need Help?

- Check the full guide: `MQTT_GUIDE.md`
- Enable debug mode in config.json
- Check logs in `%USERPROFILE%\.edcopter2.0\logs\`
