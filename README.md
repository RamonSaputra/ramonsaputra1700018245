# rahmonsaputra1700018245
-- phpMyAdmin SQL Dump
-- version 4.8.0
-- https://www.phpmyadmin.net/
--
-- Host: 127.0.0.1
-- Waktu pembuatan: 08 Mar 2019 pada 04.42
-- Versi server: 10.1.31-MariaDB
-- Versi PHP: 7.2.4

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET AUTOCOMMIT = 0;
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `sim-apotek`
--

-- --------------------------------------------------------

--
-- Struktur dari tabel `jenis_obat`
--

CREATE TABLE `jenis_obat` (
  `kode_jenis` int(10) NOT NULL,
  `nama_jenis` varchar(10) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data untuk tabel `jenis_obat`
--

INSERT INTO `jenis_obat` (`kode_jenis`, `nama_jenis`) VALUES
(101, 'Tablet'),
(102, 'Serbuk'),
(103, 'Pil'),
(104, 'Kapsul'),
(105, 'Kaplet'),
(106, 'Syrup'),
(107, 'Salep'),
(108, 'Tetes'),
(109, 'Suntik');

-- --------------------------------------------------------

--
-- Struktur dari tabel `obat`
--

CREATE TABLE `obat` (
  `nama_obat` varchar(15) NOT NULL,
  `harga_obat` int(15) NOT NULL,
  `kode_obat` int(10) NOT NULL,
  `dosis_obat` varchar(3) NOT NULL,
  `kode_jenis` int(10) NOT NULL,
  `tanggal_kadaluarsa` int(2) NOT NULL,
  `bulan_kadaluarsa` varchar(12) NOT NULL,
  `tahun_kadaluarsa` int(4) NOT NULL,
  `Stok_Obat` int(10) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data untuk tabel `obat`
--

INSERT INTO `obat` (`nama_obat`, `harga_obat`, `kode_obat`, `dosis_obat`, `kode_jenis`, `tanggal_kadaluarsa`, `bulan_kadaluarsa`, `tahun_kadaluarsa`, `Stok_Obat`) VALUES
('Konvermeks', 2500, 1, '2x3', 101, 20, 'Januari', 2020, 20),
('Paracetamol', 2500, 2, '3x1', 106, 21, 'September', 2020, 30),
('Promagh', 3500, 3, '2x1', 106, 23, 'Oktober', 2020, 25),
('Mastin', 3500, 4, '1x1', 105, 20, 'Februari', 2019, 50),
('Hemavitan', 3000, 5, '2x1', 103, 30, 'Maret', 2019, 75),
('Antimo', 5000, 6, '1x1', 101, 15, 'April', 2019, 100),
('Diapet', 4000, 7, '3x1', 106, 16, 'Mei', 2019, 10),
('Vatigon', 4500, 8, '1x1', 104, 24, 'Juni', 2019, 35),
('Oskadon', 2000, 9, '2x1', 101, 27, 'Juli', 2019, 40),
('Kalpanak', 3000, 10, '3x1', 107, 23, 'Agustus', 2019, 60),
('Mylanta', 5000, 11, '2x1', 106, 18, 'September', 2019, 70),
('Paramex', 3000, 12, '2x1', 101, 25, 'Oktober', 2019, 80),
('Procold', 4000, 13, '2x1', 101, 13, 'November', 2019, 45),
('Hemaviton', 6500, 14, '3x1', 106, 3, 'April', 2019, 55),
('Inza', 5500, 15, '3x1', 101, 7, 'Maret', 2020, 65),
('Albotil', 15000, 16, '3x1', 106, 30, 'Oktober', 2019, 40),
('Ambroxol', 11000, 17, '1x1', 101, 9, 'Juni', 2019, 25),
('Alphara', 12000, 18, '1x1', 106, 18, 'Juli', 2020, 95),
('Decolgen', 8000, 19, '3x1', 101, 19, 'Desember', 2018, 60),
('Catropile', 10000, 20, '1x1', 101, 13, 'Desember', 2018, 15),
('Amoxilin', 7000, 21, '2x1', 101, 21, 'Januari', 2019, 15),
('Neutropin', 9000, 22, '3x1', 105, 7, 'Desember', 2020, 35),
('Darsi', 13000, 23, '1x1', 105, 9, 'Februari', 2020, 115),
('Komik', 5000, 25, '3x1', 105, 9, 'April', 2020, 125);

-- --------------------------------------------------------

--
-- Struktur dari tabel `supplier`
--

CREATE TABLE `supplier` (
  `nama_pemasok` varchar(15) NOT NULL,
  `kode_obat` int(10) NOT NULL,
  `jumlah_pasok` int(10) NOT NULL,
  `nomer_telepon_supp` varchar(15) NOT NULL,
  `kode_pasok` int(10) NOT NULL,
  `harga_beli` int(11) NOT NULL,
  `tanggal_pasok` date NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
-- Dumping data untuk tabel `supplier`
--

INSERT INTO `supplier` (`nama_pemasok`, `kode_obat`, `jumlah_pasok`, `nomer_telepon_supp`, `kode_pasok`, `harga_beli`, `tanggal_pasok`) VALUES
('Terobat', 7, 30, '081227171781', 901, 3000, '2018-12-29'),
('Hexobat', 2, 25, '085646738121', 902, 1700, '2018-12-29'),
('Naobat', 1, 50, '089887766553', 903, 1500, '2018-12-30'),
('Faobat', 5, 30, '08335552278', 904, 2000, '2018-12-31'),
('Riobat', 8, 20, '08776337489', 905, 3500, '2018-12-26'),
('Faobat', 3, 30, '08335552278', 906, 2500, '2018-12-26'),
('Faobat', 4, 30, '08335552278', 907, 2500, '2018-12-26'),
('Faobat', 6, 30, '08335552278', 908, 4000, '2018-12-27'),
('Faobat', 9, 30, '08335552278', 909, 1000, '2018-12-28'),
('Faobat', 10, 30, '08335552278', 910, 2000, '2018-12-29'),
('Faobat', 11, 30, '08335552278', 911, 4500, '2018-12-30'),
('Faobat', 12, 30, '08335552278', 912, 2000, '2018-12-31'),
('Faobat', 13, 30, '08335552278', 913, 3000, '2018-12-26'),
('Faobat', 14, 30, '08335552278', 914, 5500, '2018-12-27'),
('Faobat', 15, 30, '08335552278', 915, 4500, '2018-12-28');

--
-- Indexes for dumped tables
--

--
-- Indeks untuk tabel `jenis_obat`
--
ALTER TABLE `jenis_obat`
  ADD PRIMARY KEY (`kode_jenis`);

--
-- Indeks untuk tabel `obat`
--
ALTER TABLE `obat`
  ADD PRIMARY KEY (`kode_obat`),
  ADD KEY `kode_jenis` (`kode_jenis`);

--
-- Indeks untuk tabel `supplier`
--
ALTER TABLE `supplier`
  ADD PRIMARY KEY (`kode_pasok`),
  ADD KEY `kode_obat` (`kode_obat`);

--
-- Ketidakleluasaan untuk tabel pelimpahan (Dumped Tables)
--

--
-- Ketidakleluasaan untuk tabel `obat`
--
ALTER TABLE `obat`
  ADD CONSTRAINT `obat_ibfk_1` FOREIGN KEY (`kode_jenis`) REFERENCES `jenis_obat` (`kode_jenis`);

--
-- Ketidakleluasaan untuk tabel `supplier`
--
ALTER TABLE `supplier`
  ADD CONSTRAINT `supplier_ibfk_1` FOREIGN KEY (`kode_obat`) REFERENCES `obat` (`kode_obat`);
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
