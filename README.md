<h1 align="center"> Natural Language Processing with Hugging Face Transformers </h1>
<p align="center"> Implementasi NLP menggunakan model Transformer untuk Sentiment Analysis, Summarization, dan Translation </p>

<div align="center">
<img src="https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white">
<img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54">
<img src="https://img.shields.io/badge/Hugging%20Face-ffca28?style=for-the-badge&logo=huggingface&logoColor=black">
<img src="https://img.shields.io/badge/transformers-%23F7931E.svg?style=for-the-badge&logo=transformers&logoColor=white">
</div>

---

## 📚 Deskripsi
Proyek ini menggunakan berbagai model NLP dari **Hugging Face Transformers** untuk menyelesaikan tugas-tugas bahasa alami yang umum. Dengan pipeline sederhana, kita bisa menerapkan berbagai fungsi seperti:
- **Sentiment Analysis**: Mengidentifikasi sentimen positif atau negatif dalam teks.
- **Summarization**: Menghasilkan ringkasan dari teks panjang.
- **Translation**: Menerjemahkan teks dari bahasa Indonesia ke bahasa Inggris.

---

## 🔧 Fitur Utama

### Sentiment Analysis
Mengklasifikasikan sentimen sebuah kalimat sebagai positif atau negatif dan menampilkan skor kepercayaan model.

```python
from transformers import pipeline

classifier = pipeline("sentiment-analysis")
result = classifier("Saya sangat senang dengan pengalaman ini!")[0]
print(f"Sentimen: {result['label']} (Skor Kepercayaan: {result['score']:.2f})")
```

### Summarization
Menghasilkan ringkasan yang padat dari teks panjang, sangat berguna untuk meringkas artikel atau dokumen.
```python
from transformers import pipeline

summarizer = pipeline("summarization")
text = "Teks panjang yang ingin diringkas..."
summary = summarizer(text, max_length=100, min_length=30, do_sample=False)[0]['summary_text']
print("Ringkasan:", summary)
```
### Translation (ID ➔ EN)
Menerjemahkan teks dari bahasa Indonesia ke bahasa Inggris menggunakan model terlatih.
```python
from transformers import pipeline

translator = pipeline("translation", model="Helsinki-NLP/opus-mt-id-en")
result = translator("Selamat pagi, bagaimana kabar Anda?")[0]
print("Terjemahan:", result['translation_text'])
```

🔍 Analisis & Manfaat

Mudah Digunakan:         Pipeline dari Hugging Face memudahkan pemanggilan model kompleks tanpa konfigurasi tambahan.
Kustomisasi Fleksibel:   Parameter dapat disesuaikan untuk hasil yang lebih akurat atau sesuai kebutuhan.
Penerapan Nyata:         Cocok untuk berbagai industri, seperti e-commerce, media sosial, dan penerjemahan dokumen.

📑 Referensi

Hugging Face Transformers Documentation
Model Hub for Pretrained Models

🚀 Kesimpulan

Proyek ini memanfaatkan model-model canggih dari Hugging Face untuk berbagai keperluan NLP. Dengan kemudahan penggunaan, fleksibilitas, dan hasil berkualitas tinggi, proyek ini dapat menjadi dasar bagi pengembangan aplikasi pengolahan bahasa alami yang berdaya guna tinggi.

Selamat Belajar dan Berkreasi dengan NLP! 🎉
