## python

### [public data hacking](https://github.com/defm03/public-hax)

Small bus tracking code which gets current longitude and latitude of bus from
ctabustracker. It calculates range between given point and bus actual location;
distance is returned in miles. It also displays current position of bus on map
using `google static maps` API.

usage of `urllib`, `webbrowser` and `xml.etree.ElementTree`:
```python
import urllib.request
import xml.etree.ElementTree as eltree
```
```python
# requesting page with urllib and saving to data variable
u = urllib.request.urlopen('http://ctabustracker.com/bustime/map/getBusesForRoute.jsp?route=22')
data = u.read()
```
```python
# parsing doc and going to root of xml data
doc = eltree.parse('inputfile.xml') 
root = doc.getroot()

# running findall on parsed data, and using findtext to get certain info
for bus in doc.findall('bus'):
   id_of_bus = bus.findtext('id')
   direction_of_bus = bus.findtext('d')
```
