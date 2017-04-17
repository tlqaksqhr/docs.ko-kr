---
title: "방법: 파일 압축 및 추출 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "I/O[.NET Framework], 압축"
  - "압축"
  - "파일 압축"
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
caps.latest.revision: 19
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: 파일 압축 및 추출
<xref:System.IO.Compression> 네임 스페이스는 다음 파일 및 스트림을 압축하고 압축을 푸는 형식을 포함합니다.  또한 읽고 압축된 파일의 내용을 수정 이러한 형식을 사용할 수 있습니다.  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 다음 예제에서는 보여 일부 기능이 압축 된 파일로 작업할 때 수행할 수 있습니다.  
  
## 예제  
 만들어 사용 하 여.zip 파일 이름 확장명을 가진 압축 된 파일을 추출 하는 방법을 보여 주는이 예제는 <xref:System.IO.Compression.ZipFile> 클래스입니다.  새 .zip 파일에서 폴더의 내용을 압축하고 새 폴더의 내용을 추출합니다.  <xref:System.IO.Compression.ZipFile> 클래스를 사용하기 위해, 프로젝트에서 `System.IO.Compression.FileSystem` 어셈블리를 참조해야만 합니다.  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## 예제  
 다음 예제는 .zip 파일의 내용을 반복하는 방법과 확장명이 .txt인 파일을 추출하는 방법을 보여 줍니다.  <xref:System.IO.Compression.ZipArchive> 클래스를 기존 .zip 파일에 액세스 하기 위해 사용하고, <xref:System.IO.Compression.ZipArchiveEntry> 클래스를 압축된 파일 내의 개별 항목을 검사 하기 위해 사용합니다.  <xref:System.IO.Compression.ZipArchiveEntry> 개체를 위한 확장 메서드\(<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>\) 를 사용합니다.  확장 메서드는 <xref:System.IO.Compression.ZipFileExtensions?displayProperty=fullName> 클래스에서 사용할 수 있습니다.  <xref:System.IO.Compression.ZipFileExtensions> 클래스를 사용하기 위해, 프로젝트에서 `System.IO.Compression.FileSystem` 어셈블리를 참조해야만 합니다.  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## 예제  
 다음 예제는<xref:System.IO.Compression.ZipArchive> 클래스를 사용하여 기존 .zip 파일을 액세스 하고, 압축된 파일에 새 파일을 추가합니다.  새 파일은 기존 .zip 파일에 추가 할 때 압축됩니다.  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## 예제  
 <xref:System.IO.Compression.GZipStream> 및 <xref:System.IO.Compression.DeflateStream> 클래스를 압축 데이터를 압축하고 풀기위해 사용합니다.  같은 압축 알고리즘을 사용합니다.  압축 된 <xref:System.IO.Compression.GZipStream> 에서 제공되는 방법 외에도 많은 공통 도구를 사용 하여 개체 확장명이 .gz 파일에 기록 되는 압축을 가진 파일에 쓰인 압축된 <xref:System.IO.Compression.GZipStream> 개체.  이 예제에서는 <xref:System.IO.Compression.GZipStream> 클래스를 사용하여 파일의 디렉터리를 압축하고 압축을 해제하는 방법을 보여 줍니다.  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## 참고 항목  
 <xref:System.IO.Compression.ZipArchive>   
 <xref:System.IO.Compression.ZipFile>   
 <xref:System.IO.Compression.ZipArchiveEntry>   
 <xref:System.IO.Compression.DeflateStream>   
 <xref:System.IO.Compression.GZipStream>   
 [파일 및 스트림 I\/O](../../../docs/standard/io/index.md)