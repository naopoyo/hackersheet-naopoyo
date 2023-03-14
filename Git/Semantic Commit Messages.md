---
name: "Semantic Commit Messages"
slug: "nbubbrg"
---

# Semantic Commit Messages

Format: `<type>(<scope>): <subject>`

| type       | 説明                                                                                   |
| ---------- | -------------------------------------------------------------------------------------- |
| `feat`     | ユーザー向けの新機能追加・修正。ビルドスクリプトの新機能は除く。                       |
| `fix`      | ユーザーのバグ修正。ビルドスクリプトの修正は除く。                                     |
| `docs`     | ドキュメントの変更。                                                                   |
| `style`    | セミコロンの欠落などの書式設定。プロダクションコードの変更は無し。                     |
| `refactor` | プロダクションコードのリファクタリング。変数の名前変更など。                           |
| `test`     | 不足しているテストの追加、テストのリファクタリング。プロダクションコードの変更は無し。 |
| `chore`    | ビルドスクリプトの更新など。プロダクションコードの変更は無し。                         |

参考:
- [Semantic Commit Messages](https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716)
