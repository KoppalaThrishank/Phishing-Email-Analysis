
# 📧 Email Header Analysis Guide

This project provides a step-by-step guide for analyzing email headers to detect spoofing and assess email authenticity using tools like **MXToolbox**.

## 🔍 Step 1: Open Email Header
- Click the three dots in the email client.
- Select **"Show original"**.
- Use **"Download Original"** to get `.eml` file or **"Copy to Clipboard"** for header analysis.

## 🧪 Step 2: Analyze with MXToolbox
- Paste the header into [MXToolbox Header Analyzer]

## ✅ Step 3: Check Authentication Results

### 🔐 SPF
- **SPF Alignment:** ✅ PASS if Return-Path and From domain match. ❌ Mismatch may indicate spoofing.
- **SPF Authentication:** ❌ FAIL means sender IP is unauthorized.

### 🔏 DKIM
- **DKIM Alignment:** Compare `d=` value with From domain.
- **DKIM Authentication:** ❌ FAIL if `b=` signature is not verified.

### 🛡️ DMARC
- Instructs receiver how to handle failed SPF/DKIM checks.

Example:

```

v=DMARC1; p=none; rua=mailto\:user\@example.com

```

- `p=none` – 📬 allow delivery  
- `p=quarantine` – 📥 move to spam  
- `p=reject` – 🚫 block email

## ⚠️ Step 4: Detect Spoofing
- Compare **Message ID** and **From** field.
- If different → possible spoofing attempt.

## 📊 Step 5: Understand SCL & BCL
- **SCL (Spam Confidence Level):** 🧮 Rates spam score.
- **BCL (Bulk Complaint Level):** 📦 Identifies graymail/marketing emails.

---

## 🛠️ Tools Used
- [MXToolbox]
- Email clients (Gmail, Outlook, etc.)

## 👨‍💻 Author
**Thrishank Reddy Koppala**

## 📝 License
MIT License
