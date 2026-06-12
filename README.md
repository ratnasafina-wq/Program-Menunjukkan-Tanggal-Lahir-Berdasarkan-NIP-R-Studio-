# Program-Menunjukkan-Tanggal-Lahir-Berdasarkan-NIP-R-Studio-
Program ini akan menunjukkan tanggal lahir seorang ASN berdasarkan 8 digit awal NIP diikuti dengan 10 digit NIP. Di mana, 4 digit pertama menunjukkan tahun kelahiran, 2 digit berikutnya menunjukkan bulan kelahiran, dan 2 digit berikutnya menunjukkan tanggal kelahiran.

nip <- readline(prompt = "Masukkan NIP (18 digit): ")

cat("\n")
cat("NIP          :", nip, "\n")

if (nchar(nip) != 18) {

  cat("Tanggal Lahir: NIP tidak valid! (NIP harus tepat 18 digit)\n")

} else {

  tgl_lahir <- substr(nip, 1, 8)

  tahun <- as.integer(substr(tgl_lahir, 1, 4))
  bulan <- as.integer(substr(tgl_lahir, 5, 6))
  tanggal <- as.integer(substr(tgl_lahir, 7, 8))

  if (bulan == 1) {
    nama_bulan   <- "Januari"
    maks_tanggal <- 31
  } else if (bulan == 2) {
    nama_bulan   <- "Februari"
    maks_tanggal <- 29          
  } else if (bulan == 3) {
    nama_bulan   <- "Maret"
    maks_tanggal <- 31
  } else if (bulan == 4) {
    nama_bulan   <- "April"
    maks_tanggal <- 30
  } else if (bulan == 5) {
    nama_bulan   <- "Mei"
    maks_tanggal <- 31
  } else if (bulan == 6) {
    nama_bulan   <- "Juni"
    maks_tanggal <- 30
  } else if (bulan == 7) {
    nama_bulan   <- "Juli"
    maks_tanggal <- 31
  } else if (bulan == 8) {
    nama_bulan   <- "Agustus"
    maks_tanggal <- 31
  } else if (bulan == 9) {
    nama_bulan   <- "September"
    maks_tanggal <- 30
  } else if (bulan == 10) {
    nama_bulan   <- "Oktober"
    maks_tanggal <- 31
  } else if (bulan == 11) {
    nama_bulan   <- "November"
    maks_tanggal <- 30
  } else if (bulan == 12) {
    nama_bulan   <- "Desember"
    maks_tanggal <- 31
  } else {
    nama_bulan   <- "Kode bulan pada NIP tidak valid!"
    maks_tanggal <- NA
  }

    if (is.na(maks_tanggal)) {

    cat("Tanggal Lahir:", nama_bulan, "\n")

  } else if (tanggal < 1 || tanggal > maks_tanggal) {

    cat("Tanggal Lahir: Kode tanggal pada NIP tidak valid!")

  } else {

    cat("Tanggal Lahir:", tanggal, nama_bulan, tahun, "\n")

  }
}
