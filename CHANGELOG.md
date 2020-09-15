<a name="1.2.2"></a>
# [1.2.2](https://github.com/Tylan/check_snmp_printer/compare/v1.2.1...v1.2.2) (2020-09-06)

### Features

* Added support for Kyocera printers
* Added support for Lexmark printers
* Changed perfdata to display percentage for paper tray output.  If it cannot accurate determine a percentage it is statically set based upon further inspection from other OID sources.

### Bug Fixes
* Fixed the --nofeeder option as it was removing Tray 1 even though it was not a feeder tray in some circumstances.

### Other Fixes

* Slight verbage change to some outputs
<a name="1.2.1"></a>
# [1.2.1](https://github.com/Tylan/check_snmp_printer/compare/v1.2.0...v1.2.1) (2020-08-03)

### Bug Fixes

* Fixed Brother consumable reporting as it was not reporting correctly - it is now OK or NOT OK due to OID restrictions

### Features

* Added WARNING and CRITICAL states based on certain printer messages with the messages option
<a name="1.2.0"></a>
# [1.2.0](https://github.com/Tylan/check_snmp_printer/compare/v1.1.4...v1.2.0) (2020-07-15)

### Bug Fixes

* Added library check for /usr/lib/nagios/plugins folder to support Debian systems 
* Fixed typo in OID lookup for serial number
* Fixed it so you can disable tray status warning and critical messages by setting their value to 0

### Features

* Added support for Ricoh printers 
* Added support for Brother printers
* Added the ability to disable checking of the manual feed tray

<a name="1.1.4"></a>
# [1.1.4](https://github.com/Tylan/check_snmp_printer/compare/v1.1.3...v1.1.4) (2020-01-21)

### Bug Fixes

* Fixed check for HP devices that have Image Transfer and Image Fuser Kits
* Some HP printers output Tray as TRAY - corrected this on plugin output
* Some older printers would occasionally report an SNMP genError.  Wrote a retry subroutine for this scenario

### Performance Improvements

* Search print model name first by converting to lowercase compatibility

### Features

* Added a retries option to allow for retries before timing out - defaults to 3 retries
* Added consumable support for Olivetti printers

<a name="1.1.3"></a>
# [1.1.3](https://github.com/Tylan/check_snmp_printer/compare/v1.1.2...v1.1.3) (2020-01-20)

### Bug Fixes

* Fixed Tray status for some newer HP MFPs

### Performance Improvements

* Changed code for tray size to do equations based upon specific OID outputs to determine in or mm values
* Converted to hash arrays for OID variables

### Features

* Changed pagecount to measure total B&W and total Color separately with corresponding graph modifications



<a name="1.1.2"></a>
# [1.1.2](https://github.com/Tylan/check_snmp_printer/compare/v1.1.1...v1.1.2) (2020-01-13)


### Performance Improvements

* Replaced given/when code with if/else statements for better compatibility



<a name="1.1.1"></a>
# [1.1.1](https://github.com/Tylan/check_snmp_printer/compare/v1.1.0...v1.1.1) (2020-01-13)


### Features

* Fixed a bug with HP Color LaserJet Pro M454dw toner not reporting correctly when levele are really low
* Compensated for HP Color LaserJet Pro M454dw OID .1.3.6.1.2.1.43.11.1.1.6.1 which has Magenta typo'd



<a name="1.1.0"></a>
# [1.1.0](https://github.com/Tylan/check_snmp_printer/compare/v1.0.3...v1.1.1) (2020-01-13)


### Features

* Added support for a couple more paper sizes
* Added support for more consumables (Stapler, Staples, Saddle Staples and Puncher Waste)
* Sorted display results so that CRITICAL are shown first then WARNING followed by OK

### Performance Improvements

* Fixed display output for non measurable toners
* Cleaned up code 



<a name="1.0.3"></a>
# [1.0.3](https://github.com/Tylan/check_snmp_printer/compare/v1.0.2...v1.0.3) (2019-12-26)

### Features

* Added graph support for Grafana

<a name="1.0.2"></a>
# [1.0.2](https://github.com/Tylan/check_snmp_printer/compare/v1.0.1...v1.0.2) (2019-05-27)


### Bug Fixes

* Fixed Canon consumable output display
* Fixed consumable critical detection alerts

### Features

* Added perfdata for Pagecount

### Performance Improvements

* Changed plugin newline output from \<br\> to \n



<a name="1.0.1"></a>
# [1.0.1](https://github.com/Tylan/check_snmp_printer/compare/v1.0.0...v1.0.1) (2019-05-02)

### Bug Fixes

* Fixed default SNMP version



<a name="1.0.0"></a>
# [1.0.0] (Initial Release) (2019-05-01)

* Forked from Franky Van Liedekerke version

### Bug Fixes

* Fixed status changes to properly work with Icinga

### Performance Improvements

* Made consumables and trays all or nothing for simplicity
* Added perfdata collection for consumables
* Added support for metric system output
* Better formated output strings
