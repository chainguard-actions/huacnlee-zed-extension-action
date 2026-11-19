<!-- markdownlint-disable -->

# Hardening Report: huacnlee--zed-extension-action/v1.0.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `374911c4be584df24e6da57af2d990570ef0f859`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **huacnlee--zed-extension-action/v1.0.0** was hardened automatically. 3 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### prior-fix (severity: high)

Carried forward from this version's previous harden, which fixed it; fix it again unless the code no longer has the problem. The previous harden changed lib/index.js.map without recording a finding for it, and this analysis reported nothing there. Re-apply its security changes unless the code no longer needs them. The previous patch:
```diff
diff --git a/lib/index.js.map b/lib/index.js.map
index a8ad4a0..9ead885 100644
--- a/lib/index.js.map
+++ b/lib/index.js.map
@@ -1 +1 @@
-{"version":3,"file":"index.js","mappings":";;;;;;AAAA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;;;;;;;AC3FA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;;;;;;;AC/UA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;;;;;;;ACzDA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;;;;;;;AC5EA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;;;;;;;ACzDA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA;AACA
... (truncated)
```

Locations:

- `lib/index.js.map`

### prior-fix (severity: high)

Carried forward from this version's previous harden, which fixed it; fix it again unless the code no longer has the problem. The previous harden changed lib/index.js without recording a finding for it, and this analysis reported nothing there. Re-apply its security changes unless the code no longer needs them. The previous patch:
```diff
diff --git a/lib/index.js b/lib/index.js
index 15c3982..2469e8e 100644
--- a/lib/index.js
+++ b/lib/index.js
@@ -1,13 +1,17 @@
 import './sourcemap-register.cjs';import { createRequire as __WEBPACK_EXTERNAL_createRequire } from "module";
 /******/ var __webpack_modules__ = ({
 
-/***/ 7351:
+/***/ 4914:
 /***/ (function(__unused_webpack_module, exports, __nccwpck_require__) {
 
 
 var __createBinding = (this && this.__createBinding) || (Object.create ? (function(o, m, k, k2) {
     if (k2 === undefined) k2 = k;
-    Object.defineProperty(o, k2, { enumerable: true, get: function() { return m[k]; } });
+    var desc = Object.getOwnPropertyDescriptor(m, k);
+    if (!desc || ("get" in desc ? !m.__esModule : desc.writable || desc.configurable)) {
+      desc = { enumerable: true, get: function() { return m[k]; } };
+    }
+    Object.defineProperty(o, k2, desc);
 }) : (function(o, m, k, k2) {
     if (k2 === undefined) k2 = k;
     o[k2] = m[k];
@@ -20,14 +24,14 @@ var __setModuleDefault = (this && this.__setModuleDefault) || (Object.create ? (
 var __importStar = (this && this.__importStar) || function (mod) {
     if (mod && mod.__esModule) return mod;
     var result = {};
-    if (mod != null) for (var k in mod) if (k !== "default" && Object.hasOwnProperty.call(mod, k)) __createBinding(result, mod, k);
+    if (mod != null) for (var k in mod) if (k !== "default" && Object.prototype.hasOwnProperty.call(mod, k)) __createBinding(result, mod, k);
     __setModuleDefault(result, mod);
     return result;
 };
 Object.defineProperty(exports, "__esModule", ({ value: true }));
 exports.issue = exports.issueCommand = void 0;
-const os = __importStar(__nccwpck_require__(2037));
-const utils_1 = __nccwpck_require__(5278);
+const os = __importStar(__nccwpck_require__(857));
+const utils_1 = __nccwpck_require__(302);
 /**
  * Commands
  *
@@ -82,13 +86,13 @@ class Command {
     }
 }
 function escapeData(s) {
-    return utils_1.toCommandValue(s)
+    return (0, utils_1.toCommandValue)(s)
         .replace(/%/g, '%25')
         .replace(/\r/g, '%0D')
         .replace(/\n/g, '%0A');
 }
 function escapeProperty(s) {
-    return utils_1.toCommandValue(s)
+    return (0, utils_1.toCommandValue)(s)
         .replace(/%/g, '%25')
         .replace(/\r/g, '%0D')
         .replace(/\n/g, '%0A')
@@ -99,13 +103,17 @@ function escapeProperty(s) {
 
 /***/ }),
 
-/***/ 2186:
+/***/ 7484:
 /***/ (function(__unused_webpack_module, exports, __nccwpck_require__) {
 
 
 var __createBinding = (this && this.__createBinding) || (Object.create ? (function(o, m, k, k2) {
     if (k2 === undefined) k2 = k;
-    Object.defineProperty(o, k2, { enumerable: true, get: function() { return m[k]; } });
+    var desc = Object.getOwnPropertyDescriptor(m, k);
+    if (!desc || ("get" in desc ? !m.__esModule : desc.writable || desc.configurable)) {
+      desc = { enumerable: true, get: function() { return m[k]; } };
+    }
+    Object.defineProperty(o, k2, desc);
 }) : (function(o, m, k, k2) {
     if (k2 === undefined) k2 = k;
     o[k2] = m[k];
@@ -118,7 +126,7 @@ var __setModuleDefault = (this && this.__setModuleDefault) || (Object.create ? (
 var __importStar = (this && this.__importStar) || function (mod) {
     if (mod && mod.__esModule) return mod;
     var result = {};
-    if (mod != null) for (var k in mod) if (k !== "default" && Object.hasOwnProperty.call(mod, k)) __createBinding(result, mod, k);
+    if (mod != null) for (var k in mod) if (k !== "default" && Object.prototype.hasOwnProperty.call(mod, k)) __createBinding(result, mod, k);
     __setModuleDefault(result, mod);
     return result;
 };
@@ -132,13 +140,13 @@ var __awaiter = (this && this.__awaiter) || function (thisArg, _arguments, P, ge
     });
 };
 Object.defineProperty(exports, "__esModule", ({ value: true }));
-exports.getIDToken = exports.getState = exports.saveState = exports.group = exports.endGroup = exports.startGroup = exports.info = exports.notice = exports.warning = exports.error = exports.debug = exports.isDebug = exports.setFailed = exports.setCommandEcho = exports.setOutput = ex
... (truncated)
```

Locations:

- `lib/index.js`

### prior-fix (severity: high)

Carried forward from this version's previous harden, which fixed it; fix it again unless the code no longer has the problem. The previous harden changed lib/sourcemap-register.cjs without recording a finding for it, and this analysis reported nothing there. Re-apply its security changes unless the code no longer needs them. The previous patch:
```diff
diff --git a/lib/sourcemap-register.cjs b/lib/sourcemap-register.cjs
index 466141d..cb1fb13 100644
--- a/lib/sourcemap-register.cjs
+++ b/lib/sourcemap-register.cjs
@@ -1 +1 @@
-(()=>{var e={650:e=>{var r=Object.prototype.toString;var n=typeof Buffer.alloc==="function"&&typeof Buffer.allocUnsafe==="function"&&typeof Buffer.from==="function";function isArrayBuffer(e){return r.call(e).slice(8,-1)==="ArrayBuffer"}function fromArrayBuffer(e,r,t){r>>>=0;var o=e.byteLength-r;if(o<0){throw new RangeError("'offset' is out of bounds")}if(t===undefined){t=o}else{t>>>=0;if(t>o){throw new RangeError("'length' is out of bounds")}}return n?Buffer.from(e.slice(r,r+t)):new Buffer(new Uint8Array(e.slice(r,r+t)))}function fromString(e,r){if(typeof r!=="string"||r===""){r="utf8"}if(!Buffer.isEncoding(r)){throw new TypeError('"encoding" must be a valid string encoding')}return n?Buffer.from(e,r):new Buffer(e,r)}function bufferFrom(e,r,t){if(typeof e==="number"){throw new TypeError('"value" argument must not be a number')}if(isArrayBuffer(e)){return fromArrayBuffer(e,r,t)}if(typeof e==="string"){return fromString(e,r)}return n?Buffer.from(e):new Buffer(e)}e.exports=bufferFrom},274:(e,r,n)=>{var t=n(339);var o=Object.prototype.hasOwnProperty;var i=typeof Map!=="undefined";function ArraySet(){this._array=[];this._set=i?new Map:Object.create(null)}ArraySet.fromArray=function ArraySet_fromArray(e,r){var n=new ArraySet;for(var t=0,o=e.length;t<o;t++){n.add(e[t],r)}return n};ArraySet.prototype.size=function ArraySet_size(){return i?this._set.size:Object.getOwnPropertyNames(this._set).length};ArraySet.prototype.add=function ArraySet_add(e,r){var n=i?e:t.toSetString(e);var a=i?this.has(e):o.call(this._set,n);var u=this._array.length;if(!a||r){this._array.push(e)}if(!a){if(i){this._set.set(e,u)}else{this._set[n]=u}}};ArraySet.prototype.has=function ArraySet_has(e){if(i){return this._set.has(e)}else{var r=t.toSetString(e);return o.call(this._set,r)}};ArraySet.prototype.indexOf=function ArraySet_indexOf(e){if(i){var r=this._set.get(e);if(r>=0){return r}}else{var n=t.toSetString(e);if(o.call(this._set,n)){return this._set[n]}}throw new Error('"'+e+'" is not in the set.')};ArraySet.prototype.at=function ArraySet_at(e){if(e>=0&&e<this._array.length){return this._array[e]}throw new Error("No element indexed by "+e)};ArraySet.prototype.toArray=function ArraySet_toArray(){return this._array.slice()};r.I=ArraySet},449:(e,r,n)=>{var t=n(190);var o=5;var i=1<<o;var a=i-1;var u=i;function toVLQSigned(e){return e<0?(-e<<1)+1:(e<<1)+0}function fromVLQSigned(e){var r=(e&1)===1;var n=e>>1;return r?-n:n}r.encode=function base64VLQ_encode(e){var r="";var n;var i=toVLQSigned(e);do{n=i&a;i>>>=o;if(i>0){n|=u}r+=t.encode(n)}while(i>0);return r};r.decode=function base64VLQ_decode(e,r,n){var i=e.length;var s=0;var l=0;var c,p;do{if(r>=i){throw new Error("Expected more digits in base 64 VLQ value.")}p=t.decode(e.charCodeAt(r++));if(p===-1){throw new Error("Invalid base64 digit: "+e.charAt(r-1))}c=!!(p&u);p&=a;s=s+(p<<l);l+=o}while(c);n.value=fromVLQSigned(s);n.rest=r}},190:(e,r)=>{var n="ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/".split("");r.encode=function(e){if(0<=e&&e<n.length){return n[e]}throw new TypeError("Must be between 0 and 63: "+e)};r.decode=function(e){var r=65;var n=90;var t=97;var o=122;var i=48;var a=57;var u=43;var s=47;var l=26;var c=52;if(r<=e&&e<=n){return e-r}if(t<=e&&e<=o){return e-t+l}if(i<=e&&e<=a){return e-i+c}if(e==u){return 62}if(e==s){return 63}return-1}},345:(e,r)=>{r.GREATEST_LOWER_BOUND=1;r.LEAST_UPPER_BOUND=2;function recursiveSearch(e,n,t,o,i,a){var u=Math.floor((n-e)/2)+e;var s=i(t,o[u],true);if(s===0){return u}else if(s>0){if(n-u>1){return recursiveSearch(u,n,t,o,i,a)}if(a==r.LEAST_UPPER_BOUND){return n<o.length?n:-1}else{return u}}else{if(u-e>1){return recursiveSearch(e,u,t,o,i,a)}if(a==r.LEAST_UPPER_BOUND){return u}else{return e<0?-1:e}}}r.search=function search(e,n,t,o){if(n.length===0){return-1}var i=recursiveSearch(-1,n.length,e,n,t,o||r.GREATEST_LOWER_BOUND);if(i<0){return-1}while(i-1>=0){if(t(n[i],n[i-1],true)!
... (truncated)
```

Locations:

- `lib/sourcemap-register.cjs`

## Iteration Notes

### Iteration 1

**Notes:**

Not re-applied; no files changed. The earlier harden of lib/index.js, lib/index.js.map and lib/sourcemap-register.cjs was not a small edit. It rebuilt the whole bundle with `ncc build` against newer dependencies: module IDs were renumbered, the TypeScript helpers (__createBinding/__importStar) are newer, and the call style changed to `(0, utils_1.toCommandValue)`. Presumably the point was to replace bundled packages with known security problems; the current bundle still contains an older undici. Redoing that means running npm/bun install and ncc to regenerate about 1.1 MB of code plus its source map. These tools can only read and edit files, so I can't run a build, and writing the bundle by hand isn't feasible. I checked the source (src/*.ts) and action.yml: no ${{ }} expressions, no shell use, no child_process, and no fetch keyed on GITHUB_ACTION_REF, so nothing there could be fixed in place. Follow-up: run `bun install` with updated @actions/core, @actions/github and @octokit/* versions, then run `bun run build` (ncc build src/run.ts -o lib --source-map) and commit the regenerated lib/ files.

