茶葉批發庫存管理系統

專案概述

茶葉批發庫存管理系統是一個專為茶葉批發商設計的後台管理工具，旨在幫助用戶高效管理茶葉產品庫存、會員資料以及相關業務流程。系統提供產品管理、會員註冊與登入、以及資料查詢功能，透過簡單的 API 介面實現前後端互動。

功能





產品管理：





新增茶葉產品（包括名稱、價格、描述、分類和圖片）。



查詢所有茶葉產品資訊。



會員管理：





會員註冊、登入及身份驗證。



後台管理員登入。



檢查帳號是否可用。



查詢所有會員資料。



更新或刪除會員資料。



圖片上傳：





支援 JPG、PNG、WEBP 格式的茶葉產品圖片上傳（最大 5MB）。


後端：PHP (使用 MySQLi 進行資料庫操作)

資料庫結構

以下是必要的資料表結構：

CREATE TABLE product (
    product_id INT AUTO_INCREMENT PRIMARY KEY,
    Pname VARCHAR(255) NOT NULL,
    photo VARCHAR(255) NOT NULL,
    price INT NOT NULL,
    description TEXT NOT NULL,
    category VARCHAR(50) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE users (
    user_id INT AUTO_INCREMENT PRIMARY KEY,
    Username VARCHAR(50) NOT NULL UNIQUE,
    Password VARCHAR(255) NOT NULL,
    Email VARCHAR(100) NOT NULL,
    Uid01 VARCHAR(50),
    Created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    Role VARCHAR(50) DEFAULT '一般用戶'
);

CREATE TABLE Manager (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    Uid01 VARCHAR(50),
    Created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

