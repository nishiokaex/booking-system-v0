# プロジェクト初期

## Expoプロジェクト初期化

```bash
# Expo プロジェクト作成（expo-router テンプレート使用）
npx create-expo-app@latest . --template blank

# 依存関係をインストール
npm init -y

# 開発用依存関係をインストール
npm install --save-dev oxlint@^1.7.0
```

## Pythonプロジェクト初期化

```bash
# Python仮想環境作成
python3 -m venv venv

# 仮想環境アクティベート（macOS/Linux）
source venv/bin/activate
```

## Python依存関係設定
```bash
# requirements.txt作成
cat > requirements.txt << 'EOF'
fastapi
pydantic
uvicorn
python-dotenv
EOF
# requirements-dev.txt作成
cat > requirements-dev.txt << 'EOF'
# 開発・テスト用パッケージ
# テストフレームワーク
pytest
pytest-asyncio
pytest-cov
pytest-mock

# HTTPモック用
responses==0.24.1
EOF

# Python パッケージインストール
pip3 install -r requirements.txt
pip3 install -r requirements-dev.txt
```

## 設定ファイル作成

```bash
# oxlintrc.json作成
cat > oxlintrc.json << 'EOF'
{
  "rules": {}
}
EOF

# vercel.json作成（Vercelデプロイ用）
cat > vercel.json << 'EOF'
{
  "builds": [
    {
      "src": "package.json",
      "use": "@vercel/static-build"
    },
    {
      "src": "api/index.py",
      "use": "@vercel/python"
    }
  ],
  "rewrites": [
    {
      "source": "/api/(.*)",
      "destination": "/api/index.py"
    },
    {
      "source": "/(.*)",
      "destination": "/"
    }
  ]
}
EOF
```