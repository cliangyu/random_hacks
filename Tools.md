## 🛠 Tools

### 🕸️ Computer Network

##### WDS Bridging Checklist

1. Reset WDS settings of the extended router, because the channel of the main router might has changed. If can't reset, reset the whole extended router.

2. Follow the instructions thoroughly. 

How to configure WDS function on TP-Link Wireless Routers(green UI)
https://www.tp-link.com/us/support/faq/227/

Remember to 1) change the LAN IP address of the extended router; 2) set the channel the same as the main router; 3) turn off the DHCP of the extened router.

3. If cannot connect with Ethernet LAN only, while wireless connection succeeds, it should be problems with desktop side. Follow the insturctions thoroughly.

Resetting Network Devices and Network Stack
https://www.intel.com/content/www/us/en/support/articles/000058982/wireless/intel-killer-wireless-products.html

```
Type ipconfig /release and press Enter.

Type ipconfig /flushdns and press Enter.

Type ipconfig /renew and press Enter. (This will stall for a moment.)
```