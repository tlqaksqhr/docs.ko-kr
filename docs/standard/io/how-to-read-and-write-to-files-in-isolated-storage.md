---
title: "방법: 격리된 저장소의 파일 읽기 및 쓰기 | Microsoft Docs"
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
  - "격리된 저장소를 사용하는 데이터 저장소, 파일 읽기 및 쓰기"
  - "데이터 저장소, 파일 읽기 및 쓰기"
  - "파일, 격리된 저장소"
  - "격리된 저장소, 파일 읽기 및 쓰기"
  - "데이터 읽기"
  - "저장소 내 파일 읽기"
  - "저장소, 파일 읽기 및 쓰기"
  - "격리된 저장소를 사용하여 데이터 저장, 파일 읽기 및 쓰기"
  - "저장소 내 파일에 쓰기"
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 격리된 저장소의 파일 읽기 및 쓰기
격리 된 저장소에서 파일을 읽고 쓰기 위해, 스트림 판독기 \(<xref:System.IO.StreamReader> 개체\) 를 가진 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> 개체또는 스트림 작성기 \(<xref:System.IO.StreamWriter> 개체\)를 사용합니다.  
  
## 예제  
 다음 코드 예제에서는 격리된 저장소를 가져오고 저장소에 TestStore.txt 라는 파일이 있는지 여부를 확인 합니다.  존재 하지 않는 경우, 파일을 만들고 "Hello 격리된 저장소" 라고 파일에 씁니다.  TestStore.txt가 이미 있으면, 코드 예제에서는 파일에서 읽습니다.  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## 참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>   
 <xref:System.IO.FileMode?displayProperty=fullName>   
 <xref:System.IO.FileAccess?displayProperty=fullName>   
 <xref:System.IO.StreamReader?displayProperty=fullName>   
 <xref:System.IO.StreamWriter?displayProperty=fullName>   
 [파일 및 스트림 I\/O](../../../docs/standard/io/index.md)   
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)