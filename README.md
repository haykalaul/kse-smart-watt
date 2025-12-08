# Webapps Sistem Smart Home Energy

## Gambaran Umum

Aplikasi Sistem Smart Home Energy adalah platform manajemen energi rumah tangga cerdas yang dirancang untuk membantu pengguna memantau, menganalisis, dan mengoptimalkan penggunaan energi peralatan rumah tangga. Aplikasi ini menggunakan teknologi kecerdasan buatan untuk memberikan rekomendasi personal berdasarkan pola penggunaan energi, membantu mengurangi biaya listrik dan mendukung gaya hidup berkelanjutan.

### Fitur Utama
- **Upload Data**: Unggah file CSV berisi data peralatan rumah tangga
- **Dashboard Interaktif**: Pantau penggunaan energi secara real-time
- **Analisis Penggunaan**: Analisis pola penggunaan peralatan
- **Rekomendasi AI**: Saran penghematan energi berdasarkan AI
- **Penjadwalan**: Atur jadwal penggunaan peralatan
- **Manajemen Pengguna**: Sistem autentikasi dengan akun premium

## Tech Stack

### Frontend
- **React 18** - Library JavaScript untuk UI
- **TypeScript** - Superset JavaScript dengan type safety
- **Vite** - Build tool dan development server
- **Tailwind CSS** - Framework CSS utility-first
- **Framer Motion** - Library animasi
- **React Router** - Routing untuk SPA
- **Recharts** - Library charting
- **Axios** - HTTP client
- **React Hook Form** - Form management
- **Zod** - Schema validation

### Backend
- **Go 1.22** - Bahasa pemrograman backend
- **Gin** - Web framework untuk Go
- **GORM** - ORM untuk database
- **PostgreSQL** - Database utama
- **Redis** - Database cache dan session
- **JWT** - Authentication token
- **Hugging Face API** - AI models untuk rekomendasi
- **Google OAuth** - Social login
- **SMTP** - Email service

### DevOps & Tools
- **Docker** - Containerization
- **Docker Compose** - Multi-container orchestration
- **GitHub Actions** - CI/CD pipeline
- **Systemd** - Service management
- **Nginx** - Reverse proxy
- **Netlify** - Frontend deployment

## Kebutuhan Fungsional

### 1. Manajemen Pengguna
- Registrasi dan login pengguna
- Autentikasi JWT
- OAuth login dengan Google
- Sistem premium account
- Verifikasi email

### 2. Manajemen Peralatan
- Upload data peralatan via CSV
- CRUD operations untuk peralatan
- Kategorisasi peralatan (AC, TV, Kulkas, dll.)
- Tracking penggunaan harian
- Set target penggunaan harian

### 3. Analisis dan Rekomendasi
- Analisis penggunaan energi real-time
- Deteksi overuse peralatan
- Rekomendasi penghematan berdasarkan AI
- Perhitungan biaya listrik
- Visualisasi data dengan chart

### 4. Penjadwalan
- Atur jadwal penggunaan peralatan
- Optimasi penggunaan berdasarkan tarif listrik
- Reminder dan notifikasi

### 5. Reporting
- Generate laporan PDF
- Export data analisis
- Dashboard interaktif

## Stakeholder Terlibat

### 1. Pengguna Akhir (End Users)
- **Rumah Tangga**: Pengguna individu yang ingin mengelola energi rumah
- **Keluarga**: Multiple users dalam satu rumah
- **Pemilik Properti**: Manajemen energi untuk rental property

### 2. Developer & Maintainers
- **Frontend Developer**: Mengembangkan UI/UX React
- **Backend Developer**: Mengembangkan API Go
- **DevOps Engineer**: Mengelola deployment dan infrastructure
- **Data Scientist**: Mengembangkan model AI rekomendasi

### 3. Business Stakeholders
- **Product Manager**: Mengelola roadmap produk
- **UI/UX Designer**: Mendesain interface pengguna
- **QA Engineer**: Testing dan quality assurance
- **Customer Support**: Bantuan pengguna

### 4. External Partners
- **Provider Energi**: Integrasi dengan utility companies
- **IoT Device Manufacturers**: Partnership untuk smart devices
- **AI Research Institutions**: Kolaborasi untuk model ML

## Cara Setup Local

### Prasyarat
- Node.js 18+
- Go 1.22+
- PostgreSQL 15+
- Redis
- Docker & Docker Compose (opsional)

### 1. Clone Repository
```bash
git clone <repository-url>
cd KSE\ SMART\ WATT
```

### 2. Setup Backend (Server)
```bash
cd server

# Copy environment file
cp .env.example .env

# Edit .env dengan konfigurasi database dan API keys
# Setup PostgreSQL (native atau Docker)
# Setup Redis (native atau Docker)

# Install dependencies
go mod tidy

# Run server
go run ./cmd
```

### 3. Setup Frontend (Client)
```bash
cd client

# Copy environment file
cp .env.example .env

# Edit .env dengan backend URL
# Install dependencies
npm install

# Run development server
npm run dev
```

### 4. Setup Database
```bash
# Dari direktori server/
# Jalankan init script
psql -U kse_user -d kse_smart_watt -f init_db.sql
```

### 5. Akses Aplikasi
- Frontend: http://localhost:5173
- Backend API: http://localhost:8080

## Deploy ke Netlify

### 1. Persiapan Frontend
```bash
cd client

# Build production
npm run build

# Build akan menghasilkan folder dist/
```

### 2. Deploy ke Netlify
1. **Via Netlify CLI**:
   ```bash
   # Install Netlify CLI
   npm install -g netlify-cli

   # Login ke Netlify
   netlify login

   # Deploy
   netlify deploy --prod --dir=dist
   ```

2. **Via Netlify Dashboard**:
   - Upload folder `client/dist/` ke Netlify
   - Set build command: `npm run build`
   - Set publish directory: `dist`

### 3. Konfigurasi Environment Variables
Di Netlify dashboard, set environment variables:
```
VITE_BACKEND_URL=https://your-backend-domain.com
VITE_MODE=production
```

### 4. Custom Domain (Opsional)
- Setup custom domain di Netlify
- Konfigurasi DNS records
- Enable HTTPS (otomatis oleh Netlify)

### 5. Optimasi Performance
- Enable Netlify's asset optimization
- Setup redirects dan headers
- Configure caching rules

## Lisensi

This project is licensed under the MIT License - see the LICENSE file for details.

## Kontribusi

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Support

Untuk bantuan atau pertanyaan, silakan buat issue di repository ini atau hubungi tim development.
