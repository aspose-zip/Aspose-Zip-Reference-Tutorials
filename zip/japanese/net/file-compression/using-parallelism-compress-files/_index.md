---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip パラレル圧縮を使用した C# での複数ファイルの zip 圧縮

## はじめに

**zip multiple files c#** を迅速かつ効率的に行う必要がある場合、並列処理を活用するのが最適です。最新の .NET アプリケーションでは、大規模な zip アーカイブの作成がボトルネックになることがあります—特に数十から数百のファイルを扱う場合です。Aspose.Zip for .NET は、利用可能なすべての CPU コアに作業を分散させる組み込みの **parallel zip compression** を提供することで、この問題を解消します。このチュートリアルでは、環境設定から並列処理を有効にした zip アーカイブの保存までの全プロセスを順に解説し、さらに .NET Core でスムーズに動作する **create zip archive c#** の方法も示します。

## クイック回答
- **parallel zip compression とは何ですか？** 複数のファイルを同時に圧縮し、複数のスレッドを使用して全体の処理時間を短縮します。  
- **Which .NET library supports it?** どの .NET ライブラリがサポートしていますか？ Aspose.Zip for .NET がシンプルな API で並列圧縮を提供します。  
- **Do I need a license for production?** 本番環境でライセンスが必要ですか？ はい、フルライセンスが必要です。テスト用の一時ライセンスも利用可能です。  
- **Can I add files to zip on the fly?** 実行時にファイルを zip に追加できますか？ もちろんです—追加したい各ファイルに対して `Archive.CreateEntry` を使用します。  
- **Is it compatible with .NET 6/7?** .NET 6/7 と互換性がありますか？ はい、API はすべての最新 .NET ランタイムで動作します。

## zip multiple files c# とは？
`zip multiple files c#` は、C# コードを使用して多数の個別ファイルを含む単一の ZIP アーカイブを作成することを指します。これに **parallel zip compression** を組み合わせると、ライブラリは各ファイルを別々のスレッドで処理し、最終アーカイブの生成にかかる時間を劇的に短縮します。

## なぜ Aspose.Zip のパラレル圧縮を使用するのか？
並列圧縮を使用すると、マルチプロセッサマシンのすべてのコアを活用でき、単一スレッド方式に比べて **2‑3 倍高速** のスループットを実現します。また、スケーラビリティも優れており、ファイル数を増やしても実時間が比例して増加せず、API がスレッド管理を行うため、ビジネスロジックに集中できます。  

- **Speed:** すべての論理プロセッサを活用し、一般的なワークロードで zip 作成時間を最大 70 % 短縮します。  
- **Scalability:** 500 ファイル以上のバッチでも CPU 時間が比例して増加しません。  
- **Simplicity:** 高レベルメソッドが `System.Threading.Tasks` の複雑さを隠蔽します。  
- **Flexibility:** .NET Framework 2.0–4.8.1、.NET Core 2.0–3.1、.NET 5–10（.NET 6/7 を含む）をサポートし、クラウドネイティブサービスに対応します。

## 前提条件

- C# と .NET 開発の基本的な知識。  
- Aspose.Zip for .NET がインストールされていること。**[here](https://releases.aspose.com/zip/net/)** からダウンロードできます。  
- 一時ライセンスまたはフルライセンス（このチュートリアルでは一時ライセンスで十分です）。

## 名前空間のインポート

`Aspose.Zip` 名前空間には、ZIP アーカイブ操作に必要なすべての型が含まれています。  

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

まず、必要な名前空間を C# ファイルにインポートし、コンパイラが使用するクラスの場所を認識できるようにします。

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## 手順 1: ドキュメントディレクトリの設定

圧縮したいファイルが格納されているフォルダーを定義します。このパスは `dataDir` 変数に格納され、ディスク上の任意の場所を指すことができます。

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## 手順 2: 圧縮プロセスの初期化

書き込み用に新しい ZIP ファイルを開きます。`using` 文により、操作後にファイルストリームが適切に破棄され、ファイルハンドルのリークを防止します。

```csharp
using (FileStream zipStream = new FileStream("output.zip", FileMode.Create))
{
    // Archive instance will be created inside the using block
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## 手順 3: ファイルを並列で読み込み圧縮する

`Parallel.ForEach` は、反復が複数のスレッドで同時に実行される可能性がある foreach ループを実行します。  

アーカイブに追加する各ソースファイルを開きます。この例では 2 つの古典テキストを使用していますが、任意の数のドキュメントに対して **add files to zip** できます。`Parallel.ForEach` ループは作業を自動的にスレッドに分配します。

```csharp
var files = Directory.GetFiles(dataDir);
Parallel.ForEach(files, filePath =>
{
    // Read and add each file inside the parallel loop
});
```

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## 手順 4: アーカイブエントリの作成

`Archive` クラスは、構築中の ZIP コンテナを表す Aspose.Zip の最上位オブジェクトです。  

`CreateEntry` は、指定されたファイルの新しいエントリを ZIP アーカイブに作成します。`CreateEntry` の呼び出しごとに、アーカイブに新しいファイルエントリが追加されます。

```csharp
Archive archive = new Archive(zipStream);
archive.CreateEntry(fileName, fileStream);
```

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## 手順 5: 並列性基準の定義

`ParallelOptions` は、並列ループの実行方法を制御する .NET 型です。  

`ParallelOptions` を設定して圧縮を並列で実行するよう構成します。`ParallelCompressInMemory` フラグは Aspose.Zip に常に並列処理を使用させ、`MaxDegreeOfParallelism` は同時スレッド数の上限を設定できます。

```csharp
ParallelOptions options = new ParallelOptions
{
    MaxDegreeOfParallelism = Environment.ProcessorCount // use all cores
};
archive.ParallelCompressInMemory = true;
archive.ParallelOptions = options;
```

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## 手順 6: 圧縮アーカイブの保存

最後に、エンコーディング、コメント、先に定義した並列設定など、希望のオプションでアーカイブをディスクに書き込みます。`Save` メソッドが ZIP ファイルを確定します。

```csharp
archive.Save();
```

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Pro tip:** 非常に大きなファイルを圧縮する場合、`ParallelOptions.MaxDegreeOfParallelism` を論理プロセッサ数未満の値に設定することを検討してください。これにより、負荷がかかってもサーバーの応答性を保てます。

### 一般的な使用例

- **Batch reporting:** 下流システム向けに日次 CSV レポートの zip バンドルを生成します。  
- **Document archiving:** バックアップ用に多数の PDF、画像、ログを単一のアーカイブに保存します。  
- **Data export APIs:** 複数のデータファイルを含む zip ファイルを単一の HTTP 応答でクライアントに返します。  

## よくある問題とヒント

- **Memory pressure on huge files:** ファイル全体をメモリに読み込むのではなく、チャンク単位でストリーミングするか、`ParallelCompressInMemory` モードを選択的に使用してください。  
- **Thread safety:** Aspose.Zip API は並列モードでスレッドセーフですが、圧縮中に外部から同じ `FileStream` を変更しないでください。  
- **Performance tuning:** 共有サーバーで CPU 使用率を制限したい場合は、`ParallelOptions.MaxDegreeOfParallelism` を調整してみてください。  

## よくある質問

**Q: Aspose.Zip for .NET を他の圧縮ライブラリと併用できますか？**  
A: はい、Aspose.Zip は他の .NET ライブラリと共存できます。名前空間を分けて使用してください。

**Q: テスト用の一時ライセンスは利用できますか？**  
A: はい、**[here](https://purchase.aspose.com/temporary-license/)** からテスト用の一時ライセンスを取得できます。

**Q: 問題が発生した場合、どこでサポートを受けられますか？**  
A: コミュニティサポートとディスカッションは **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** をご利用ください。

**Q: さらにコード例や詳細な API ドキュメントはどこで見つけられますか？**  
A: 包括的な例は **[Aspose.Zip documentation](https://reference.aspose.com/zip/net/)** をご覧ください。

**Q: Aspose.Zip のフルライセンスはどこで購入できますか？**  
A: Aspose.Zip for .NET は **[here](https://purchase.aspose.com/buy)** から購入できます。

**最終更新日:** 2026-06-09  
**テスト環境:** Aspose.Zip 24.11 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [zip multiple files c# – Aspose.Zip for .NET を使用した手軽な圧縮](/zip/net/file-compression/compress-multiple-files/)
- [Aspose.Zip for .NET を使用して Zip アーカイブを作成しファイルを追加する方法](/zip/net/file-compression/compress-single-file/)
- [Aspose.Zip .NET で暗号化付き複数ファイルを圧縮する](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}