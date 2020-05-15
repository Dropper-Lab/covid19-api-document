[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![HitCount](http://hits.dwyl.io/Dropper-Lab/covid19-api-document.svg)](http://hits.dwyl.io/Dropper-Lab/covid19-api-document)
![GitHub last commit](https://img.shields.io/github/last-commit/Dropper-Lab/covid19-api-document.svg)

[Korean](./README-ko_KR.md) | [English](./README-en_EN.md)

# covid19-api-document
The API document for COVID19 API from Dropper Lab.

## Source Code

- [covid19-status-crawler](https://github.com/Dropper-Lab/covid19-status-crawler)
	- Crawling trends of occurrence by city and province in Korea.
- [covid19-foreign-crawler](https://github.com/Dropper-Lab/covid19-foreign-crawler)
	- Crawling trends of occurrence by nation.
- [covid19-data-checker](https://github.com/Dropper-Lab/covid19-data-checker)
	- Check the data and fix it when it has problem.
- [api-log-custodian](https://github.com/Dropper-Lab/api-log-custodian)
	- Manage folders for log data and check the capacity of the log data.
- [python-mail-sender](https://github.com/Dropper-Lab/python-mail-sender)
	- Mail sender package.
- [api-request-conut-resetor](https://github.com/Dropper-Lab/api-request-conut-resetor)
	- Reset api request count.

## Crontab Automation

All source codes have to be located in same folder. (In following case, source codes are in home/nulleekh/.)

```
57 * * * * cd home/nulleekh/ ; python3.6 api-log-custodian.py
0 * * * * cd home/nulleekh/ ; python3.6 status_crawler.py ; python3.6 foreign_crawler.py
3 * * * * cd home/nulleekh/ ; python3.6 data_checker.py
0 15 * * * cd home/nulleekh/ ; python3.6 requestcount_resetor.py
```

## Patch Note

### v1.0.0
- Initial release

### v1.0.1
- Add Yemen to supported country.
- Update return field and return example of II.
- Modify attribute name on III.

### v1.0.2
- Add etc, tajikistan, comoros to supported country.
- Fix small errors in supported country.

### v1.0.3
- Remove unsupported countries from supported country.

### v1.0.4
- Add description about source code and crontab automation.
- Add lesotho to supported country.