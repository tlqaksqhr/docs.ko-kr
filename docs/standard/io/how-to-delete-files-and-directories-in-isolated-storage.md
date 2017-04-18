---
title: "방법: 격리된 저장소의 파일 및 디렉터리 삭제 | Microsoft Docs"
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
  - "격리된 저장소를 사용하는 데이터 저장소, 파일 및 디렉터리 삭제"
  - "디렉터리[.NET Framework], 격리된 저장소"
  - "파일[.NET Framework], 격리된 저장소"
  - "격리된 저장소, 파일 및 디렉터리 삭제"
  - "데이터 저장소, 파일 및 디렉터리 삭제"
  - "저장소, 파일 및 디렉터리 만들기"
  - "격리된 저장소 파일 내 파일 삭제"
  - "격리된 저장소를 사용하여 데이터 저장, 파일 및 디렉터리 삭제"
  - "격리된 저장소 파일 내 디렉터리 삭제"
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 격리된 저장소의 파일 및 디렉터리 삭제
격리된 저장소 파일 내에서 디렉터리와 파일을 삭제할 수 있습니다.  저장소 내에서, 파일 및 디렉터리 이름은 운영 체제 종속적 이며 가상 파일 시스템의 루트를 기준으로 지정 됩니다.  Windows 운영 체제에서 대\/소문자를 구분 하지 않습니다.  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=fullName>클래스는 디렉토리와 파일을 삭제하는 두 메서드를 제공합니다: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> 및 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.  존재하지 않는 파일 또는 디렉터리를 삭제하려고 하면  <xref:System.IO.IsolatedStorage.IsolatedStorageException> 예외가 throw됩니다.  이름에 와일드 카드 문자를 포함 하는 경우 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A>는 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 예외를 throw하고,<xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>는 <xref:System.ArgumentException> 예외를 throw 합니다.  
  
 디렉터리에 파일 또는 하위 디렉터리가 포함된 경우에는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A>메서드가 실패합니다.  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> 및 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A>메서드를 기존 파일 및 디렉토리를 검색하기 위해 사용합니다.  저장소의 가상 파일 시스템을 검색 하는 방법에 대한 자세한 내용은 [방법: 격리된 저장소의 기존 파일 및 디렉터리 찾기](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md) 을 참조하십시오.  
  
## 예제  
 다음 코드 예제에서는 몇 개의 디렉터리와 파일을 만든 다음 삭제합니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## 참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=fullName>   
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)