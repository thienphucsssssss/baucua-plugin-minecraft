Bầu Cua Tôm Cá ![Supported server version](https://img.shields.io/badge/minecraft-1.21+-brightgreen)
===========

Plugin trò chơi dân gian Bầu Cua Tôm Cá cho server Minecraft. Người chơi đặt cược, lắc xúc xắc, và nhận thưởng ngay trong game. Có chế độ chơi Solo và chế độ Nhà Cái (mở phòng cho nhiều người).

Tính năng
===========

**Chế độ Solo (Free)**
- Người chơi mở bàn solo bằng `/baucua`, đặt cược và lắc ngay
- Giới hạn cược tối thiểu / tối đa
- Thuế lợi nhuận khi thắng (tùy chỉnh %)
- Cooldown giữa các ván
- Lịch tự động bật/tắt Solo theo ngày giờ (VD: cuối tuần 19h–24h)
- Hiệu ứng lắc xúc xắc với animation + âm thanh

**Chế độ Nhà Cái (✨ Premium)**
- Người chơi mở phòng làm nhà cái, người khác tham gia đặt cược
- Giới hạn số người chơi mỗi phòng (mặc định 7)
- Nhà cái đặt giới hạn cược riêng cho phòng
- Phòng tự đóng sau thời gian cài đặt (mặc định 20 phút)
- Cảnh báo trước khi phòng hết hạn
- Giao diện duyệt phòng (Room Browser) — xem người chơi, giới hạn, trạng thái
- Thông báo toàn server khi có phòng mới mở
- Hiển thị lịch sử của 5 cầu gần nhất.

**Chung**
- Giao diện chest GUI đẹp mắt, dễ dùng
- Tùy chỉnh toàn bộ tin nhắn, prefix, âm thanh
- Hỗ trợ kinh tế qua Vault (tương thích mọi plugin kinh tế)
- Hỗ trợ ItemsAdder (tùy chọn)

Hướng dẫn sử dụng
===========

**Cần có:**

- [Paper](https://papermc.io/) 1.21+
- [Vault](https://www.spigotmc.org/resources/vault.34315/) + một plugin kinh tế (EssentialsX, CMI,...)
- (Tùy chọn) [ItemsAdder](https://www.spigotmc.org/resources/itemsadder.73355/)

**Cài đặt:**

1. Bỏ `BauCua.jar` vào `plugins/`
2. Khởi động server — plugin tự tạo `config.yml`
3. Chỉnh cấu hình theo ý muốn, rồi `/baucua reload`

**Danh sách lệnh:**

| Lệnh | Chức năng | Quyền |
|---|---|---|
| `/baucua` | Mở bàn Solo | baucua.play |
| `/baucua help` | Xem trợ giúp | baucua.play |
| `/baucua create [tên] [giới hạn]` | Mở phòng nhà cái | ✨ Premium |
| `/baucua join <tên phòng>` | Tham gia phòng | ✨ Premium |
| `/baucua rooms` | Mở giao diện duyệt phòng | ✨ Premium |
| `/baucua list` | Xem danh sách phòng (text) | ✨ Premium |
| `/baucua leave` | Rời phòng đang tham gia | ✨ Premium |
| `/baucua delete` | Đóng phòng (chủ phòng) | ✨ Premium |
| `/baucua solo <on\|off\|status>` | Bật/tắt chế độ Solo | baucua.admin |
| `/baucua reload` | Tải lại cấu hình | baucua.admin |

> Alias: `/bc` tương đương `/baucua`

**Cấu hình:**

Plugin chỉ có 1 file `config.yml`, mọi cài đặt nằm trong đó:

```yaml
baucua:
  solo-enabled: true           # Bật/tắt Solo thủ công
  min-bet: 1000                # Cược tối thiểu
  max-bet: 100000              # Cược tối đa (-1 = không giới hạn)
  tax-percent: 10              # Thuế lợi nhuận khi thắng
  cooldown-seconds: 3          # Thời gian chờ giữa các ván
  animation-duration-ticks: 40 # Thời gian lắc xúc xắc
  max-players-per-room: 7      # Số người chơi tối đa mỗi phòng
  room-lifetime-minutes: 20    # Phòng tự đóng sau X phút

  # Lịch tự bật/tắt Solo theo ngày giờ
  solo-auto-schedule:
    enabled: false
    timezone: "Asia/Saigon"
    windows:
      - days: ["SATURDAY", "SUNDAY"]
        start: "19:00"
        end: "24:00"
```

Luật chơi
===========

Bầu Cua Tôm Cá là trò chơi dân gian Việt Nam:
- Bàn chơi có **6 linh vật**: Bầu, Cua, Tôm, Cá, Gà, Nai
- Người chơi **đặt tiền vào linh vật** mình muốn (được chọn nhiều linh vật)
- Lắc **3 viên xúc xắc** — mỗi viên hiện 1 linh vật
- Mỗi linh vật trùng thì **được × 1 lần cược**. Trùng 2 viên → ×2, trùng 3 → ×3
- Không trùng → **mất tiền cược** ở linh vật đó

Hình ảnh
===========
<img width="533" height="422" alt="baucuasolo" src="https://github.com/user-attachments/assets/b019c5d2-514b-4d33-ad3d-f17cbe721511" />

<img src="https://s5.ezgif.com/tmp/ezgif-54eacbbb171d158c.gif" width="60%">

<img width="993" height="60" alt="baucuatime" src="https://github.com/user-attachments/assets/5928fa73-9848-4e3b-b7e4-10b8a7d05e12" />

<img width="527" height="273" alt="sanhbaucua" src="https://github.com/user-attachments/assets/079559e4-ce2d-41c0-a449-fee0a1b98d18" />

<img width="703" height="569" alt="baurooms" src="https://github.com/user-attachments/assets/048254e9-cd25-4b13-a05b-a4fa907142e5" />

<img width="537" height="418" alt="nhacai" src="https://github.com/user-attachments/assets/20439dd9-acd2-45a8-9a5a-b9e5e4b55f59" />

<img width="715" height="419" alt="nguoichoi" src="https://github.com/user-attachments/assets/655e417f-0469-4d33-97ce-c2232c2b3593" />

---

Liên hệ **Discord: lilarie** để mua License-key bản Premium mở khóa chế độ Nhà Cái và duyệt phòng ủng hộ mình, cảm ơn đã đọc ☕️.
