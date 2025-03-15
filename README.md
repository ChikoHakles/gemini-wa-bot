## 📲 WhatsApp Chatbot with Gemini AI & Time API  

This is a **WhatsApp chatbot** that integrates **Google Gemini AI**, **whatsapp-web.js**, and **timeapi.io** to provide intelligent responses, handle customer inquiries, and display real-time Jakarta time.  

---

## 🚀 Features  

✅ **AI-Powered Responses** – Uses **Google Gemini AI** for smart replies.  
✅ **WhatsApp Automation** – Built with **whatsapp-web.js**.  
✅ **Real-Time Time API** – Fetches **current time in Jakarta (GMT+7)** from **timeapi.io**.  
✅ **Automated Customer Support** – Handles FAQs, greetings, and payments.  
✅ **Dynamic Image URLs** – Stores greeting and payment image URLs in **.env**.  
✅ **QR Code Payment Support** – Sends payment QR codes to users.  

---

## 🛠️ Installation  

### 1️⃣ **Clone the Repository**  
```bash
git clone https://github.com/wimboro/wa-bot-Gemini-AI.git
cd wa-bot-Gemini-AI
```

### 2️⃣ **Install Dependencies**  
```bash
npm install
```

### 3️⃣ **Setup `.env` File**  
Create a `.env` file and add:  
```env
GEMINI_API_KEY=your_gemini_api_key
GREETING_IMAGE_URL=https://your-image-url.com/greeting.jpg
PAYMENT_IMAGE_URL=https://your-image-url.com/payment.jpg
```

### 4️⃣ **Configure `replies.js`**  
Edit `replies.js` to customize bot responses:  

```javascript
module.exports = {
  greetingsCaption: "Your custom greeting caption here.",
  paymentCaption: "Your custom payment caption here.",
  options: "Pilih opsi:\n1. Info E-meterai\n2. Cara beli\n3. Harga\n4. Pengiriman\n5. Pengembalian\n6. Pembayaran\n\nKetik nomor opsi.",
  faq: {
    "apa itu e-meterai": "E-meterai adalah cap elektronik untuk dokumen resmi.",
    "bagaimana cara membeli": "Beli E-meterai via situs kami atau layanan pelanggan.",
    "harga": "Harga E-meterai bervariasi. Hubungi kami untuk harga terbaru.",
    "waktu pengiriman": "Pengiriman E-meterai: 2-3 hari kerja.",
    "kebijakan pengembalian": "Jaminan uang kembali 30 hari jika tidak puas."
  },
  stopMessage: "Bot berhenti. Ketik \"lanjut\" untuk melanjutkan.",
  continueMessage: "Bot telah dilanjutkan. Bagaimana saya bisa membantu Anda?",
  continuePrompt: "Anda terhubung dengan asisten otomatis. Ketik \"stop\" untuk berhenti atau abaikan untuk melanjutkan.",
  defaultMessage: "Maaf, saya tidak mengerti pertanyaan Anda. Silakan coba lagi atau hubungi customer service kami.",
  optionResponses: {
    1: "E-meterai adalah cap elektronik untuk dokumen digital.",
    2: "Anda bisa membeli E-meterai melalui situs kami atau customer service.",
    3: "Harga E-meterai adalah Rp. 17,000.",
    4: "Pengiriman E-meterai dilakukan dalam 2-3 hari kerja.",
    5: "Kami memberikan jaminan pengembalian dalam 30 hari jika tidak puas."
  }
};
```

### 5️⃣ **Customize `prompt_template.js`**  
Edit `prompt_template.js` to customize AI prompt behavior:  

```javascript
const emeteraiPromptTemplate = `
You are a customer service representative for E-meterai, an electronic stamp solution for digital document authentication. Your goal is to provide accurate and helpful information about E-meterai to users.

Key points:
- E-meterai secures digital documents with cryptography.
- Benefits: enhanced security, easy verification, and reduced fraud risk.
- Compatible with PDF, Word, and image files.
- API available for integration.

Current Date & Time: {current_time}

User question: {user_question}

Your response:
`;

module.exports = emeteraiPromptTemplate;
```

### 6️⃣ **Run the Bot**  
```bash
node index.js
```
Scan the QR code displayed in the terminal to authenticate your WhatsApp.  

---

## 📌 Usage  

### 🔹 **Basic Commands**  
- `halo`, `assalamualaikum`, `selamat` → Sends a greeting with an image.  
- `pembayaran`, `bayar` → Sends a payment QR code.  
- `bantuan` → Displays available options.  
- `stop` → Stops bot responses.  
- `lanjut` → Resumes bot responses.  

### 🔹 **AI-Powered Responses**  
- The bot uses **Google Gemini AI** to generate responses for general questions about **E-meterai**.  
- If a user asks for the current time, the bot fetches the **real-time Jakarta time (GMT+7)** from **timeapi.io** and responds accordingly.  

---

## 🔧 Project Structure  

```
📂 wa-bot-Gemini-AI/
│── 📜 index.js            # Main bot logic  
│── 📜 replies.js          # Predefined bot responses  
│── 📜 prompt_template.js  # AI prompt structure  
│── 📜 .env                # API keys and configurations  
│── 📜 package.json        # Node.js dependencies  
│── 📜 README.md           # Project documentation  
```

---

## 🔥 Dependencies  

- [whatsapp-web.js](https://github.com/pedroslopez/whatsapp-web.js) – WhatsApp automation  
- [dotenv](https://www.npmjs.com/package/dotenv) – Manages environment variables  
- [axios](https://www.npmjs.com/package/axios) – Handles HTTP requests (for **timeapi.io**)  
- [GoogleGenerativeAI](https://www.npmjs.com/package/@google/generative-ai) – Gemini AI integration  
- [qrcode-terminal](https://www.npmjs.com/package/qrcode-terminal) – Displays QR code in terminal  

---

## 🤝 Contributing  

1. Fork this repository.  
2. Create a new branch: `git checkout -b feature-branch`.  
3. Commit changes: `git commit -m "Added a new feature"`.  
4. Push your branch: `git push origin feature-branch`.  
5. Open a Pull Request.  

---

## 📜 License  

This project is licensed under the **MIT License**.  

---

## 📞 Contact  

📧 Email: wgp.pra@gmail.com  
🐦 Twitter: [@galasaktii](https://twitter.com/galasaktii)  
📌 GitHub: [wimboro](https://github.com/wimboro)  

---