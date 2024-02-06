## Dockerで実行する場合
以下、`${TAG}` の部分は、M1 Macなどarm64アーキテクチャの場合は `arm64` 、それ以外の場合（x86_64）は `v2` としてください。

例： docker pull takakoron/pags_bioinfo2023:v2

```bash
docker pull takakoron/pags_bioinfo2022:${TAG}
git https://github.com/tmochidu/pags_bioinfo2023.git
cd 2-3
docker run -p 8888:8888 -v $(PWD):/work/scRNAseq_handson takakoron/pags_bioinfo2023:${TAG} bash -c "export PS1=dummy && source /root/.bashrc && jupyter notebook --ip=0.0.0.0 --port=8888 --allow-root"

```
出力されたリンク（ http://127.0.0.1:8888/ ...のほう）をブラウザで開けば置いてあるipynb実行できます。
