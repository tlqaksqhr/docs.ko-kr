---
title: "방법: 격리된 저장소에 파일 및 디렉터리 만들기 | Microsoft Docs"
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
  - "디렉터리[.NET Framework], 격리된 저장소"
  - "파일[.NET Framework], 격리된 저장소"
  - "격리된 저장소, 파일 및 디렉터리 만들기"
  - "데이터 저장소, 파일 및 디렉터리 만들기"
  - "격리된 저장소를 사용하는 데이터 저장소, 파일 및 디렉터리 만들기"
  - "저장소, 파일 및 디렉터리 만들기"
  - "격리된 저장소를 사용하여 데이터 저장, 파일 및 디렉터리 만들기"
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 격리된 저장소에 파일 및 디렉터리 만들기
격리된 저장소를 가져온 다음에는 데이터를 저장할 디렉터리와 파일을 만들 수 있습니다.  저장소 내에서 파일 및 디렉터리 이름은 가상 파일 시스템의 루트와 관련하여 지정됩니다.  
  
 디렉터리를 만들려면 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=fullName> 인스턴스 메서드를 사용하십시오.  존재하지 않은 디렉터리의 하위 디렉터리를 지정하기 위해 두 디렉터리가 모두 만들어 집니다.  이미 있는 디렉터리를 지정하기 위해 디렉터리를 만들지 않고 예외가 throw 되지 않은 상태로 메서드를 반환합니다.  그러나 잘못된 문자를 포함하는 디렉터리 이름을 지정할 경우, <xref:System.IO.IsolatedStorage.IsolatedStorageException> 예외가 throw 됩니다.  
  
 파일을 만들기 위해 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=fullName> 메서드를 사용합니다.  
  
 Windows 운영 체제에서, 격리된 저장소 파일 및 디렉터리 이름은 대\/소문자 구분 됩니다.  즉, `ThisFile.txt`라는 파일을 만든 다음 `THISFILE.TXT`라는 다른 파일을 만들면, 한 파일만 만들어집니다.  파일 이름은 표시를 위해 원래의 대\/소문자를 그대로 유지합니다.  
  
## 예제  
 다음 코드 예제에서는 격리된 저장소에서 파일과 디렉터리를 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## 참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>   
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)