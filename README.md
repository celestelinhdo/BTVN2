<!doctype html>
<html lang="vi">
<head>
  <meta charset="utf-8">
  <meta name="viewport"
        content="width=device-width, initial-scale=1">
  <title>Cổng tài liệu mô phỏng</title>
  <style>
    body {
      margin: 0;
      background: #f7b7c4;
      color: #e880ab;
      font-family: “EB Garamond”, Georgia;
    }
    main { max-width: 1000px; margin: 32px auto; padding: 0 16px; }
    h1 { color:#b94f70; }
    a { color: #e880ab; }
    .layout {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
    }
    .panel { min-width: 0; padding: 20px; background: #ffffff; }
    @media (max-width: 600px) {
      .layout { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>
  <main>
    <h1>Cổng tài liệu đại biểu</h1>
    <p>Hội nghị bắt đầu lúc <strong>09:00</strong>.</p>
 <p>Phòng họp: <strong>B203</strong>.</p>

    <div class="layout">
      <section class="panel">
        <h2>Tài liệu đại biểu</h2>
        <p>Đọc sổ tay trước khi tham dự.</p>
        <a href="files/handbook-v1.1.pdf">
          Mở sổ tay đại biểu – bản 1.1
        </a>
      </section>
      <section class="panel">
        <h2>Lượt đăng ký mới theo tháng</h2>
        <p>Số liệu minh họa. Đơn vị tính là lượt đăng ký.</p>
        <canvas id="bieu-do" role="img"
                aria-label="Lượt đăng ký mới theo tháng"></canvas>
<p class="tong-so">Tổng số lượt đăng ký sau cập nhật: 200 lượt.</p>
      </section>
<section class="panel">
        <h2>Liên hệ ban tổ chức</h2>
        <p>Người phụ trách: Đỗ Hoàng Linh</p>
        <p>
          Email:
          <a href="mailto:dsc.dav@gmail.com">
            dsc.dav@gmail.com
          </a>
        </p>
        <p>
          Điện thoại:
          <a href="tel:0123456789">
            0123 456 789
          </a>
        </p>
      </section>
    </div>
  </main>

  <script src="https://cdn.jsdelivr.net/npm/chart.js@4"></script>
  <script>
    const soLieu = [
      { thang: "Tháng 7", giaTri: 24 },
      { thang: "Tháng 8", giaTri: 37 },
      { thang: "Tháng 9", giaTri: 42 },
      { thang: "Tháng 10", giaTri: 51 },
{ thang: "Tháng 11", giaTri: 46 }
    ];

    const loaiBieuDo = "line";
    const mauChinh = "#f7b7c4";
    const bangMau = [mauChinh, "#e89aaa", "#b88aae", "#e7b96f", "#8faeb5" ];

    new Chart(document.getElementById("bieu-do"), {
      type: loaiBieuDo,
      data: {
        labels: soLieu.map(muc => muc.thang),
        datasets: [{
          label: "Lượt đăng ký mới",
          data: soLieu.map(muc => muc.giaTri),
          backgroundColor: loaiBieuDo === "line"
            ? bangMau
            : mauChinh,
          borderColor: mauChinh
        }]
      }
    });
  </script>
</body>
</html>
