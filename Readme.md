# 🇹🇭 thai-id-reader

![License](https://img.shields.io/badge/license-MIT-green)
![Node.js >=16](https://img.shields.io/badge/node-%3E=16.0.0-brightgreen)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)

A Node.js library for reading Thai national ID cards using a PC/SC smart card reader.
Returns parsed data in clean JSON format with name, gender, address, and more.

## Table of Contents

- [🇹🇭 thai-id-reader](#-thai-id-reader)
  - [Table of Contents](#table-of-contents)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Sample Output](#sample-output)
  - [Features](#features)
  - [License](#license)

---


## Installation

```bash
npm install thai-id-reader
```

Requires pcsclite-compatible smart card reader and driver installed.

## Usage

```js
const { readThaiIdCard } = require("thai-id-reader");

readThaiIdCard()
  .then((data) => {
    console.log("✅ Thai ID Card Data:", data);
  })
  .catch((err) => {
    console.error("❌ Failed to read card:", err.message);
  });
```

## Sample Output
```json
{
  "cid": "1234567890123",
  "fullNameThai": {
    "title": "นาย",
    "firstname": "สมชาย",
    "lastname": "ใจดี"
  },
  "fullNameEng": {
    "title": "Mr.",
    "firstname": "Somchai",
    "lastname": "Jaidee"
  },
  "gender": "ชาย",
  "birthDate": "01 Jan 2540",
  "issueDate": "15 Mar 2565",
  "expiryDate": "15 Mar 2575",
  "address": {
    "houseNo": "99/1",
    "moo": "5",
    "soi": "สุขสบาย 10",
    "road": "พหลโยธิน",
    "subDistrict": "ลาดยาว",
    "district": "จตุจักร",
    "province": "กรุงเทพมหานคร",
    "postcode": "10900"
  }
}
```

## Features

- ✅ Read Thai citizen ID card via Smart Card Reader
- ✅ Decode TIS-620 Thai characters
- ✅ Auto-format address & split full name
- ✅ Automatic postal code lookup from Excel dataset
- ✅ Supports Windows, macOS, Linux (with PC/SC)

## License
MIT © 2025 Chawit Tanachochaow