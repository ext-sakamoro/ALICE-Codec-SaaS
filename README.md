# ALICE-Codec SaaS

Hyper-fast 3D wavelet video codec API

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum, ALICE-Codec |

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST /api/v1/encode` | 動画フレームエンコード |
| `POST /api/v1/decode` | エンコードデータからフレーム復元 |
| `GET  /api/v1/formats` | 対応フォーマット一覧 |
| `GET`  | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
