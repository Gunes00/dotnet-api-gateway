# .NET API Gateway 🚪

Mikroservis mimarisi için modern, performanslı ve güvenli bir API Gateway.

![.NET](https://img.shields.io/badge/-.NET%206.0-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/-C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

## 📋 Proje Özeti

Bu API Gateway, mikroservis mimarisinde farklı servislere gelen istekleri yönlendiren, kimlik doğrulama, yetkilendirme, hız sınırlama ve önbelleğe alma gibi çapraz kesit endişelerini (cross-cutting concerns) merkezi olarak yöneten bir servis geçididir.

## ✨ Özellikler

- 🔐 JWT tabanlı kimlik doğrulama ve yetkilendirme
- 🔄 İstek yönlendirme ve yük dengeleme
- 📊 İstek/yanıt dönüşümleri ve validasyonları
- ⏱️ Hız sınırlama ve kota yönetimi
- 📝 Kapsamlı loglama ve izleme
- 🛡️ API güvenliği (CORS, XSS koruması)
- 🚀 Yüksek performans ve ölçeklenebilirlik
- 🐳 Docker ve Kubernetes desteği

## 🧩 Mimari

```
+-------------------+
|    API Gateway    |
+-------------------+
         |
         ▼
+-------------------+
|  Servis Registry  |
+-------------------+
         |
         ▼
+-------------------+     +-------------------+     +-------------------+
|   Servis A (Auth) |     | Servis B (Users)  |     | Servis C (Data)   |
+-------------------+     +-------------------+     +-------------------+
```

## 🔧 Teknolojiler

- ASP.NET Core 6.0
- Ocelot (API Gateway framework)
- IdentityServer4 (Kimlik doğrulama)
- Entity Framework Core
- Redis (Önbelleğe alma)
- Serilog (Loglama)
- Docker & Docker Compose
- Azure DevOps / GitHub Actions

## 🚀 Başlangıç

### Gereksinimler

- .NET 6.0 SDK
- Docker (isteğe bağlı)
- SQL Server (veya başka bir veritabanı)

### Kurulum

```bash
# Repo'yu klonlayın
git clone https://github.com/Gunes00/dotnet-api-gateway.git

# Proje dizinine gidin
cd dotnet-api-gateway

# Bağımlılıkları yükleyin ve derleyin
dotnet restore
dotnet build

# Uygulamayı çalıştırın
dotnet run --project src/ApiGateway/ApiGateway.csproj
```

### Docker ile Çalıştırma

```bash
# Docker imajını oluşturun
docker build -t api-gateway .

# Konteyneri çalıştırın
docker run -p 5000:80 api-gateway
```

## 📁 Proje Yapısı

```
/
├── src/
│   ├── ApiGateway/             # Ana API Gateway projesi
│   ├── AuthService/            # Kimlik doğrulama servisi
│   ├── Common/                 # Paylaşılan kod ve yardımcı sınıflar
│   └── ServiceRegistry/        # Servis kaydı ve keşif
├── tests/                      # Birim ve entegrasyon testleri
├── docker/                     # Docker yapılandırması
├── docs/                       # Dokümantasyon
└── scripts/                    # Yardımcı scriptler
```

## 📝 Yapılacaklar

- [ ] GraphQL desteği
- [ ] WebSocket gateway desteği
- [ ] Daha fazla servis entegrasyonu
- [ ] Gelişmiş izleme ve metrikler
- [ ] Azure/AWS entegrasyonları

## 📄 Lisans

MIT