# 📚 The Canonical Hadith Library (Kutub al-Hadith) with Translations

A production-grade, highly structured, standardized JSON dataset of the 11 major canonical Hadith collections, containing over **73,198 Hadiths** and **1,614 Chapters** across Arabic, Urdu, and English. Designed for mobile applications (Flutter, React Native, Swift, Kotlin), web platforms, and research applications.

---

## 🌟 Highlights

- **Complete Canonical Corpus**: Includes the *Sihah Sittah* (The Six Major Books), *Musnad Ahmad*, *Mishkat al-Masabih*, *Silsilah as-Sahiha*, *Muwatta Malik*, and *Forty Hadith of Imam Nawawi*.
- **Standardized Schema**: Consistent schema across all 11 collections with unified IDs, hadith numbers, international numbering, and metadata.
- **Multi-Script Arabic**: Both vowelled Arabic (*with Tashkeel*) and clean Arabic (*without Tashkeel*) to enable lightning-fast full-text search and fuzzy matching.
- **Tri-Lingual Content**: Authentic Arabic text paired with authoritative Urdu and English translations.
- **Comprehensive Exegesis Fields**: Includes sanad / isnad narrations, chapter headers (*Baab*), authenticity status codes, cross-references (*Takhreej*), and detailed explanations (*Wazahat*).
- **Flexible File Formats**:
  - `complete.json`: Master file per collection bundling all fields for single-file ingestion.
  - `arabic.json`, `urdu.json`, `english.json`: Lightweight language-specific JSON files for apps that load translations on demand.
  - `chapters.json`: Table of contents with chapter IDs, names, and Hadith counts.
  - `metadata.json`: High-level book statistics, author details, and file mappings.
- **GitHub Friendly**: All individual files are kept well within GitHub's standard limits (under 65 MB), eliminating Git LFS bandwidth quotas and allowing direct consumption via `raw.githubusercontent.com`.

---

## 📊 Canonical Collections Overview

| # | Collection Folder | English Name | Urdu Name | Arabic Name | Total Hadiths | Chapters | Arabic | Urdu | English |
|---|-------------------|--------------|-----------|-------------|---------------|----------|:------:|:----:|:-------:|
| 1 | `01_sahih_bukhari` | Sahih al-Bukhari | صحیح بخاری | صحيح البخاري | 7,563 | 99 | ✅ | ✅ | ✅ |
| 2 | `02_sahih_muslim` | Sahih Muslim | صحیح مسلم | صحيح مسلم | 7,564 | 56 | ✅ | ✅ | ✅ |
| 3 | `03_sunan_abi_dawood` | Sunan Abi Dawood | سنن ابی داؤد | سنن أبي داود | 5,274 | 43 | ✅ | ✅ | ✅ |
| 4 | `04_jami_at_tirmidhi` | Jami' at-Tirmidhi | جامع ترمذی | جامع الترمذي | 3,956 | 50 | ✅ | ✅ | ✅ |
| 5 | `05_sunan_an_nasai` | Sunan an-Nasa'i | سنن نسائی | سنن النسائي | 5,761 | 53 | ✅ | ✅ | ✅ |
| 6 | `06_sunan_ibn_majah` | Sunan Ibn Majah | سنن ابن ماجہ | سنن ابن ماجه | 4,341 | 39 | ✅ | ✅ | ✅ |
| 7 | `07_musnad_ahmad` | Musnad Ahmad ibn Hanbal | مسند احمد | مسند أحمد بن حنبل | 28,199 | 1,176 | ✅ | ✅ | ➖ |
| 8 | `08_mishkat_al_masabih` | Mishkat al-Masabih | مشکوٰۃ المصابیح | مشكاة المصابيح | 6,294 | 29 | ✅ | ✅ | ➖ |
| 9 | `09_silsilah_as_sahiha` | Silsilat al-Ahadith as-Sahiha | سلسلہ احادیث صحیحہ | سلسلة الأحاديث الصحيحة | 3,704 | 28 | ✅ | ✅ | ➖ |
| 10 | `10_muwatta_malik` | Muwatta Malik | موطأ امام مالک | موطأ الإمام مالك | 500 | 40 | ✅ | ➖ | ✅ |
| 11 | `11_forty_hadith_nawawi` | An-Nawawi's Forty Hadith | اربعین نووی | الأربعون النووية | 42 | 1 | ✅ | ➖ | ✅ |
| **Total** | | | | | **73,198** | **1,614** | | | |

---

## 📂 Repository Structure

```
Hadith-Text-With-Translations/
├── hadith_manifest.json          # Master manifest for all 11 books, counts & file paths
├── 01_sahih_bukhari/
│   ├── complete.json             # Unified: Arabic, Urdu, English, Baab, Sanad, Takhreej
│   ├── arabic.json               # Arabic text with & without tashkeel
│   ├── urdu.json                 # Urdu translation & narration
│   ├── english.json              # English translation
│   ├── chapters.json             # Chapter listing with Hadith ranges
│   └── metadata.json             # Book metadata and author details
├── 02_sahih_muslim/              # [Same structure]
├── 03_sunan_abi_dawood/          # [Same structure]
├── 04_jami_at_tirmidhi/          # [Same structure]
├── 05_sunan_an_nasai/            # [Same structure]
├── 06_sunan_ibn_majah/           # [Same structure]
├── 07_musnad_ahmad/              # Complete, Arabic, Urdu, Chapters, Metadata
├── 08_mishkat_al_masabih/        # Complete, Arabic, Urdu, Chapters, Metadata
├── 09_silsilah_as_sahiha/        # Complete, Arabic, Urdu, Chapters, Metadata
├── 10_muwatta_malik/             # Complete, Arabic, English, Chapters, Metadata
├── 11_forty_hadith_nawawi/       # Complete, Arabic, English, Chapters, Metadata
├── .gitignore
└── README.md
```

---

## 📝 Data Schema

### 1. `complete.json` Record Schema

Each entry in `complete.json` represents a fully resolved Hadith record:

```json
{
  "record_id": 1,
  "hadith_number": 1,
  "international_number": 1,
  "chapter_id": 1,
  "chapter": "کتاب وحی کے بیان میں",
  "baab": "رسول اللہ ﷺ پر وحی کی ابتداء کیسے ہوئی",
  "narrator": "ہم کو حمیدی نے یہ حدیث بیان کی...",
  "status": 1,
  "takhreej": "وقول الله جل ذكره: {إنا أوحينا إليك كما أوحينا إلى نوحٍ والنبيين من بعده}:",
  "wazahat": "اور اللہ عزوجل کا یہ فرمان...",
  "arabic": "حَدَّثَنَا الْحُمَيْدِيُّ عَبْدُ اللَّهِ بْنُ الزُّبَيْرِ ، قَالَ : حَدَّثَنَا سُفْيَانُ... إِنَّمَا الْأَعْمَالُ بِالنِّيَّاتِ...",
  "arabic_without_tashkeel": "حدثنا الحميدي عبد الله بن الزبير ، قال : حدثنا سفيان... انما الاعمال بالنيات...",
  "urdu": "آپ ﷺ فرما رہے تھے کہ ’’ تمام اعمال کا دارومدار نیت پر ہے...‘‘",
  "english": "Narrated 'Umar bin Al-Khattab: I heard Allah's Apostle saying, 'The reward of deeds depends upon the intentions...'"
}
```

| Field | Type | Description |
|---|---|---|
| `record_id` | `integer` | Unique sequential identifier within the book. |
| `hadith_number` | `integer` | Traditional Hadith numbering within the collection. |
| `international_number` | `integer` | Globally standardized Hadith numbering. |
| `chapter_id` | `integer` | Foreign key matching `chapters.json -> chapter_id`. |
| `chapter` | `string` | Chapter title in Urdu. |
| `baab` | `string` | Sub-chapter / thematic section header. |
| `narrator` | `string` | Sanad / isnad chain and introductory context. |
| `status` | `integer` | Authenticity classification code (e.g. 1 = Sahih). |
| `takhreej` | `string` | Cross-references to Quranic verses or other Hadith collections. |
| `wazahat` | `string` | Explanatory notes and scholarly commentary. |
| `arabic` | `string` | Full Arabic text with vowel diacritics (*Tashkeel*). |
| `arabic_without_tashkeel` | `string` | Clean Arabic text stripped of diacritics for fast search. |
| `urdu` | `string` | Authorized Urdu translation. |
| `english` | `string` | Authorized English translation (where available). |

---

### 2. `chapters.json` Schema

```json
[
  {
    "chapter_id": 1,
    "chapter_number": 1,
    "chapter_urdu": "کتاب وحی کے بیان میں",
    "chapter_english": "THE BOOK OF REVELATION.",
    "total_hadiths": 7
  }
]
```

---

## 🚀 How to Use in Your App

### 1. Flutter / Dart

Fetch and parse Hadiths on the fly directly via GitHub Raw URLs:

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

class HadithService {
  static const String baseUrl =
      'https://raw.githubusercontent.com/muqeetiqbal2/Hadith-Text-With-Translations/main';

  /// Load master manifest containing stats and paths for all 11 books
  static Future<Map<String, dynamic>> fetchManifest() async {
    final response = await http.get(Uri.parse('$baseUrl/hadith_manifest.json'));
    if (response.statusCode == 200) {
      return jsonDecode(response.body);
    }
    throw Exception('Failed to load Hadith manifest');
  }

  /// Load chapter table of contents for a book
  static Future<List<dynamic>> fetchChapters(String bookFolder) async {
    final response = await http.get(Uri.parse('$baseUrl/$bookFolder/chapters.json'));
    if (response.statusCode == 200) {
      return jsonDecode(response.body);
    }
    throw Exception('Failed to load chapters for $bookFolder');
  }

  /// Load English translation for Sahih al-Bukhari
  static Future<List<dynamic>> fetchEnglishHadiths(String bookFolder) async {
    final response = await http.get(Uri.parse('$baseUrl/$bookFolder/english.json'));
    if (response.statusCode == 200) {
      return jsonDecode(response.body);
    }
    throw Exception('Failed to load English hadiths');
  }
}
```

### 2. TypeScript / React / Node.js

```typescript
interface HadithManifest {
  collection_title: string;
  total_books: number;
  total_hadiths: number;
  books: Array<{
    book_id: number;
    book_key: string;
    folder: string;
    title_english: string;
    total_hadiths: number;
    total_chapters: number;
  }>;
}

const RAW_URL = 'https://raw.githubusercontent.com/muqeetiqbal2/Hadith-Text-With-Translations/main';

async function getHadithBook(folder: string) {
  const res = await fetch(`${RAW_URL}/${folder}/complete.json`);
  if (!res.ok) throw new Error(`HTTP ${res.status}: ${res.statusText}`);
  return await res.json();
}

async function searchHadith(query: string, folder = '01_sahih_bukhari') {
  const hadiths = await getHadithBook(folder);
  const normalized = query.trim().toLowerCase();
  
  return hadiths.filter((h: any) => 
    h.english?.toLowerCase().includes(normalized) ||
    h.urdu?.includes(query) ||
    h.arabic_without_tashkeel?.includes(query)
  );
}
```

### 3. Python

```python
import requests

BASE_URL = "https://raw.githubusercontent.com/muqeetiqbal2/Hadith-Text-With-Translations/main"

# Fetch Nawawi's 40 Hadith in English & Arabic
response = requests.get(f"{BASE_URL}/11_forty_hadith_nawawi/complete.json")
hadiths = response.json()

for h in hadiths[:5]:
    print(f"Hadith #{h['hadith_number']}: {h['english'][:100]}...\n")
```

---

## 🔗 Related Repositories

- [The Noble Qur'an Dataset (Text, Translations, Tafseer & Word-by-Word)](https://github.com/muqeetiqbal2/Quran-Text-with-Translations-And-Tafsirs)

---

## 📜 License & Acknowledgements

The texts, translations, and commentaries compiled in this dataset are part of public Islamic heritage. All formatting, structuring, JSON normalization, and manifests are open for personal, educational, and commercial applications.
