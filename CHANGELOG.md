<a name="1.1.4"></a>
# [1.1.4](https://github.com/Tylan/check_snmp_printer/compare/1.1.3...1.1.4) (2020-01-21)

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
# [1.1.3](https://github.com/Tylan/check_snmp_printer/compare/1.1.2...1.1.3) (2020-01-20)

### Bug Fixes

* Fixed Tray status for some newer HP MFPs

### Performance Improvements

* Changed code for tray size to do equations based upon specific OID outputs to determine in or mm values
* Converted to hash arrays for OID variables

### Features

* Changed pagecount to measure total B&W and total Color separately with corresponding graph modifications



<a name="1.1.2"></a>
# [1.1.2](https://github.com/Tylan/check_snmp_printer/compare/1.1.1...1.1.2) (2020-01-13)


### Performance Improvements

* Replaced given/when code with if/else statements for better compatibility



<a name="1.1.1"></a>
# [1.1.1](https://github.com/Tylan/check_snmp_printer/compare/1.1.0...1.1.1) (2020-01-13)


### Features

* Fixed a bug with HP Color LaserJet Pro M454dw toner not reporting correctly when levele are really low
* Compensated for HP Color LaserJet Pro M454dw OID .1.3.6.1.2.1.43.11.1.1.6.1 which has Magenta typo'd



<a name="1.1.0"></a>
# [1.1.0](https://github.com/Tylan/check_snmp_printer/compare/1.0.3...1.1.1) (2020-01-13)


### Features

* Added support for a couple more paper sizes
* Added support for more consumables (Stapler, Staples, Saddle Staples and Puncher Waste)
* Sorted display results so that CRITICAL are shown first then WARNING followed by OK

### Performance Improvements

* Fixed display output for non measurable toners
* Cleaned up code



<a name="1.0.3"></a>
# [1.0.3](https://github.com/Tylan/check_snmp_printer/compare/1.0.2...1.0.3) (2019-12-26)

### Features

* Added graph support for Grafana

<a name="1.0.2"></a>
# [1.0.2](https://github.com/Tylan/check_snmp_printer/compare/1.0.1...1.0.2) (2019-05-27)


### Bug Fixes

* Fixed Canon consumable output display
* Fixed consumable critical detection alerts

### Features

* Added perfdata for Pagecount

### Performance Improvements

* Changed plugin newline output from \<br\> to \n



<a name="1.0.1"></a>
# [1.0.1](https://github.com/Tylan/check_snmp_printer/compare/1.0.0...1.0.1) (2019-05-02)

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
