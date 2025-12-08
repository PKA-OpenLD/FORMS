# Changelog

Tất cả thay đổi quan trọng trong dự án FORMS (Flood and Outage Risk Management System) sẽ được ghi chép tại đây.

Định dạng dựa trên [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
và dự án tuân theo [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.1.0] - 2024-12-07

### ✨ Added (Tính năng mới)

- **Logo & Branding**: Thêm logo FORMS chính thức vào README và tài liệu
- **Demo Video**: Thêm video demo trực quan (GIF) giới thiệu các tính năng chính của hệ thống
- **Mục lục tương tác**: Bổ sung Table of Contents với quick navigation links trong README
- **FAQ Section**: Thêm phần câu hỏi thường gặp bao gồm 8 câu hỏi phổ biến:
  - Hướng dẫn sử dụng Bun runtime
  - Yêu cầu GPU cho AI model
  - Tích hợp VietMap API
  - Hỗ trợ Raspberry Pi
  - License dataset và sensor integration
- **Contributing Guidelines**: Cải thiện hướng dẫn đóng góp với quy trình báo cáo issue chi tiết
- **External Resources**: Thêm danh sách liên kết tài liệu tham khảo hữu ích

### 📝 Changed (Thay đổi)

- **README Restructure**: Tổ chức lại cấu trúc README với các section rõ ràng hơn:
  - Phần giới thiệu tính năng được mở rộng và chi tiết hơn
  - Kiến trúc hệ thống với ASCII diagram trực quan
  - Cải thiện phần deployment và configuration
- **License Section**: Format lại phần License với thông tin rõ ràng về third-party components
- **Contact Info**: Cập nhật thông tin liên hệ và GitHub organization
- **Version Badge**: Cập nhật badge hiển thị version 1.1.0

### 🐛 Fixed (Sửa lỗi)

- Loại bỏ các section rỗng trong README
- Sửa lỗi hiển thị demo video
- Cập nhật links không còn hoạt động

### 📚 Documentation

- Làm rõ quy trình clone repository với submodules
- Cải thiện hướng dẫn cài đặt dependencies cho từng module
- Thêm ví dụ cấu hình chi tiết cho .env files
- Bổ sung disclaimer về mục đích sử dụng cho học tập

### 🔧 Internal

- Clean up các thông tin OLP 2025 competition không cần thiết
- Tối ưu hóa cấu trúc markdown để dễ đọc hơn
- Chuẩn hóa format của CONTRIBUTING.md

---

## [1.0.0] - 2024-12-06

### 🎉 Initial Release (Phát hành đầu tiên)

Phiên bản đầu tiên của FORMS - Hệ thống Quản lý Rủi ro Ngập lụt và Tắc đường.

### ✨ Core Features (Tính năng chính)

#### 🗺️ Real-time Interactive Map

- Hiển thị bản đồ tương tác với VietMap GL JS
- Cập nhật vị trí ngập lụt và tắc đường theo thời gian thực
- WebSocket support cho live updates
- Responsive design trên mọi thiết bị

#### 📡 IoT Sensor Integration

- Hỗ trợ kết nối cảm biến mực nước, nhiệt độ, độ ẩm
- MQTT protocol communication
- Go-based MQTT bridge middleware
- Tự động cảnh báo khi cảm biến vượt ngưỡng

#### 🤖 AI Computer Vision

- YOLOv8/v11 model để nhận diện 8 loại phương tiện
- Real-time traffic density monitoring
- Tự động phát hiện và cảnh báo tắc đường
- Hỗ trợ multiple camera sources

#### ⚙️ Rule Engine & Automation

- Visual workflow editor với drag-and-drop interface
- Tạo rules tự động với AND/OR logic operators
- Auto-generate warning zones khi sensors trigger
- Flexible rule configuration

#### 👥 Crowdsourcing System

- Cho phép người dùng báo cáo tình trạng ngập/tắc
- Phân loại mức độ nghiêm trọng (low/medium/high/critical)
- Status tracking và cập nhật real-time
- User report management dashboard

#### 🌦️ Weather Integration

- Tích hợp Weather API để dự báo thời tiết
- Dự đoán rủi ro ngập lụt dựa trên dữ liệu thời tiết
- Early warning system
- Historical weather data analysis

#### 🎛️ Admin Dashboard

- Quản lý zones, sensors, và rules
- Analytics dashboard với charts và statistics
- User reports moderation
- System health monitoring

### 🏗️ Architecture (Kiến trúc)

#### Web Application (`/app`)

- **Framework**: Next.js 16 với Bun runtime
- **Frontend**: React 19 với TypeScript
- **UI Components**: Shadcn/ui, Tailwind CSS
- **Maps**: VietMap GL JS integration
- **Real-time**: WebSocket server (Bun)
- **Database**: MongoDB với Mongoose ODM
- **State Management**: React Context API

#### MQTT Bridge (`/bridge`)

- **Language**: Go (Golang)
- **Protocol**: MQTT Client library
- **Function**: Middleware kết nối IoT sensors với Web API
- **Features**:
  - Topic mapping configuration
  - Automatic sensor data forwarding
  - Error handling và reconnection logic

#### AI Models (`/models`)

- **Framework**: Python với YOLOv8/v11
- **CV Library**: OpenCV
- **Features**:
  - Vehicle detection và classification
  - Traffic density calculation
  - Congestion detection algorithm
  - Training pipeline for custom datasets

### 📦 Infrastructure

- **Database**: MongoDB for data persistence
- **Message Queue**: MQTT Broker (Mosquitto)
- **Containerization**: Docker support
- **Deployment**: Docker Compose configuration

### 📄 Documentation (Tài liệu)

- Comprehensive README với tiếng Việt
- Installation guide cho từng module
- Configuration examples
- API documentation skeleton
- Architecture diagrams

### ⚖️ Legal & Licensing

- **License**: Apache License 2.0
- **NOTICE file**: Attribution cho third-party components
- **Dataset License**: CC BY 4.0 (Roboflow Universe)
- **Open Source Compliance**: Tuân thủ license của dependencies

### 🔧 Development Tools

- Git submodules cho microservices architecture
- Environment configuration templates (.env.example)
- Development và production build scripts
- Code organization theo best practices

### 🚀 Getting Started

- Clone repository với `--recursive` flag cho submodules
- Hướng dẫn cài đặt dependencies:
  - Bun cho Web App
  - Go modules cho Bridge
  - Python virtualenv cho AI Models
- Docker-compose setup cho quick start
- Configuration guides cho các API keys

### 🎯 Target Use Cases

- Giám sát ngập lụt đô thị real-time
- Quản lý giao thông thông minh
- Early warning system cho thiên tai
- Crowdsourced data collection
- IoT sensor network management

### 🏆 Competition Ready

- Dự án hoàn chỉnh cho OLP 2025
- Phần mềm nguồn mở - Smart City theme
- Sử dụng dữ liệu mở (Open Data)
- Documentation đầy đủ bằng tiếng Việt

---

## Release Notes Summary

### Version Comparison

| Feature            | 1.0.0       | 1.1.0            |
| ------------------ | ----------- | ---------------- |
| Core System        | ✅ Complete | ✅ Stable        |
| Documentation      | ✅ Basic    | ✅ Enhanced      |
| Visual Assets      | ❌ None     | ✅ Logo + Demo   |
| Contributing Guide | ⚠️ Basic    | ✅ Detailed      |
| FAQ Section        | ❌ None     | ✅ Added         |
| External Links     | ⚠️ Limited  | ✅ Comprehensive |

---

## Links

- **Repository**: [github.com/PKA-OpenLD/FORMS](https://github.com/PKA-OpenLD/FORMS)
- **Issues**: [GitHub Issues](https://github.com/PKA-OpenLD/FORMS/issues)
- **Contributing**: [CONTRIBUTING.md](./CONTRIBUTING.md)
- **License**: [LICENSE](./LICENSE)

---

_Changelog được cập nhật bởi PKA-OpenLD Team_
