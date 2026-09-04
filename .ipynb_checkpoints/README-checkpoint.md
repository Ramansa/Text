# DevSuite

> A lightweight, privacy-first, 100% client-side developer utility suite built with vanilla HTML5, CSS3, and modern JavaScript. Zero external dependencies, zero trackers, and zero server roundtrips.

---

## Overview

**DevSuite** runs entirely inside your browser sandbox. Whether you need to format nested PHP/HTML/JS templates, inspect JSON Web Tokens, encode Unicode strings with emojis into Base64, or calculate cryptographic SHA/MD5 digests, all operations execute locally in memory.

---

## Features

### Multi-Language Code Formatter & Minifier
* **Auto-Detection**: Heuristically detects JavaScript, HTML, CSS, PHP, and SQL.
* **Nested Syntax Isolation**: Correctly isolates and formats inline `<style>` CSS and `<script>` JavaScript inside HTML documents without corrupting surrounding markup.
* **Hybrid PHP Templating**: Handles mixed PHP tags (`<?php ... ?>`, `<?= ... ?>`) interleaved with HTML, CSS, and JS.
* **Minification Engine**: Strips single-line and multi-line comments and eliminates unnecessary whitespace across supported languages.

### Cryptography & Hashes
* **WebCrypto SubtleCrypto API**: Native, hardware-accelerated generation of **SHA-1**, **SHA-256**, and **SHA-512** digests.
* **Vanilla JS MD5 Engine**: Offline RFC 1321 MD5 calculation without external libraries.
* **All Hashes Generator**: Parallel generation of all four hash digests simultaneously for instant checksum comparisons.
* **JWT Inspector**: Splits dot-separated Base64URL tokens to parse Header and Payload claims, calculating UTC expiration dates and active/expired status badges.

### Encoders & Decoders
* **Unicode / UTF-8 Base64**: Uses `TextEncoder` and `TextDecoder` byte streaming to prevent `btoa` Latin1 errors when encoding emojis, symbols, and multi-byte scripts.
* **URL Encoder / Decoder**: RFC 3986 percent-encoding and decoding for query strings and parameters.
* **HTML Entities**: Two-way conversion between reserved symbols (`<`, `>`, `&`, `"`, `'`) and safe numeric/named entities to mitigate XSS.

### Text Transformers
* **Smart Propercase / Title Case**: Editorial-compliant casing (Chicago Manual of Style / AP Stylebook) that keeps minor words (*of*, *in*, *the*, *and*, *for*) in lowercase unless at boundaries.
* **Case Converters**: Instant transformations for `UPPERCASE`, `lowercase`, and `Sentence case`.

### JSON Utilities
* **JSON Beautifier**: Indent with 2 spaces, 4 spaces, or tabs.
* **JSON Minifier**: One-line structural compression removing all non-functional whitespace.

### UI & Workspace
* **Theme Studio**: 6 built-in color schemes (*Midnight Blue, Onyx Dark, Clean Light, Cyber Neon, Forest Emerald, Dracula*) plus custom HEX color customization.
* **Split Workspace**: Side-by-side input/output panels with live character, word, line, and byte counters.
* **Local Persistence**: Drafts, selected languages, indentation preferences, and theme choices are preserved locally via `localStorage`.

---

## Technical Specifications

| Feature | Implementation | Standard / Reference |
| :--- | :--- | :--- |
| **Cryptography** | `crypto.subtle.digest` & Bitwise Adders | FIPS PUB 180-4 / RFC 1321 |
| **JWT Parsing** | Safe Base64URL translation + JSON tree | RFC 7519 / RFC 7515 |
| **Base64** | `Uint8Array` + `TextEncoder` / `TextDecoder` | RFC 4648 |
| **Title Casing** | Lexical boundary regex matching | Chicago Manual of Style §8.155 |
| **Code Formatting** | Multi-tiered token masking & recursive indentation | W3C / ECMAScript Standards |

---

## Getting Started

Because DevSuite requires no build steps, node modules, or bundlers, deployment is as simple as opening a single file:

1. **Download** or clone the repository:
   ```bash
   git clone [https://github.com/Ramansa/Text.git](https://github.com/Ramansa/Text.git)
