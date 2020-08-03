1. 硬體 && 用戶加入 => POST /api/v2/users

   - 加入成功 (201)
   - 重複加入 (409)
   - 存在異常 (500)

2. 硬體 && 權限檢查 => GET /api/v2/users/:id/auth

   - { 用戶資料 } (200)
   - 用戶尚未加入 (401)
   - 用戶尚未完成實體註冊 (403)
   - 用戶權限遭移除 (403)
   - 存在異常 (500)

3. 前台 && 取得所有用戶 => GET /api/v2/users

   - { 全部用戶 } (200)
   - 存在異常 (500)

4. 前台 && 取得指定用戶 => GET /api/v2/users/:userid

   - { 指定用戶 } (200)
   - 存在異常 (500)

5. 前台 && 刪除指定用戶 => DELETE /api/v2/users/:id

   - 刪除成功 (200)
   - 存在異常 (500)

6. 前台 && 實體用戶註冊 => PATCH /api/v2/users/:id

   - 註冊成功 (200)
   - 重複註冊 (409)
   - 存在異常 (500)

7. 前台 && 調整訪問權限 => PATCH /api/v2/users/:id/auth

   - 調整成功 (200)
   - 存在異常 (500)

---

1. 前台 && 發送郵件 => POST /api/v2/mail

   - 發送成功 (200)
   - 存在異常 (500)

---

1. 前台 && 圖片上傳 => POST /api/v2/upload

   - 不支援的檔案格式 (415)
   - 超過圖片限制大小 (413)
   - { 圖片連結 } (201)
   - 存在異常 (500)

---

1. 前台 && 管理員註冊 => POST /api/v2/admin/signup

   - 註冊成功 (201)
   - 重複註冊 (409)
   - 存在異常 (500)

2. 前台 && 管理員登入 => POST /api/v2/admin/login

   - 帳號或密碼錯誤 (401)
   - { 管理員資料 } (200)
   - 存在異常 (500)

3. 前台 && 檢查是否持續登入 => POST /api/v2/admin/check

   - 未帶有訪問令牌 (401)：交由 error handler
   - 無效的訪問令牌 (401)：交由 error handler
   - 成功 (200)

4. 前台 && 管理員登出 => POST /api/v2/admin/logout

   - 已登出 (200)