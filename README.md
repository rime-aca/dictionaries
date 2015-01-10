Rime 擴充詞庫
===========

## 使用方法

1.  下載詞庫 https://github.com/rime-aca/dictionaries.git (或是直接 clone / pull 這個 repo)

    注意到其中應該有六個檔案：

    ```
    double_pinyin.custom.yaml
    luna_pinyin.custom.yaml
    luna_pinyin.hanyu.dict.yaml
    luna_pinyin.cn_en.dict.yaml
    luna_pinyin.extended.dict.yaml
    luna_pinyin.poetry.dict.yaml*
    ```

2.  將上述檔案中後面五個移至你的 Rime 目錄底下 (depends on your OS)，以 OS X 來說，就是在 `~/Library/Rime/` 底下

    ```
    # 部署位置：
    # ~/.config/ibus/rime  (Linux)
    # ~/Library/Rime  (Mac OS)
    # %APPDATA%\Rime  (Windows)
    ```

3.  若爲雙拼使用者，請將 `double_pinyin.custom.yaml` 改名成你所使用的雙拼方案的代碼
    如 `double_pinyin_abc.custom.yaml`，並放入第二步所說的目錄底下
    若該目錄底下已有這個檔案，那麼將這兩個檔案中的內容 merge 即可

    附雙拼方案與其對應的 id 一覽表：

| 輸入方案   | id                 |
|------------|--------------------|
| 自然碼雙拼 | double_pinyin      |
| 智能ABC雙拼| double_pinyin_abc  |
| 小鶴雙拼   | double_pinyin_flypy|
| MSPY雙拼   | double_pinyin_mspy |


## 增加自己的詞庫

在這個架構底下增加自己的詞庫相當容易，只需新增一個自訂的 `*.dict.yaml` 檔案，如 `lazywei.dict.yaml`
然後在 `luna_pinyin.extended.dict.yaml` 的 `import_tables` 底下加上你的字典名稱，例如我的例子中就是

```
  - lazywei
```

而 `lazywei.dict.yaml` 的內容就可以仿照 `luna_pinyin.hanyu.dict.yaml` 等檔案的內容了，惟需注意：本詞庫升級時需重新修改 `import_tables`，若有更好解法請不吝分享。
