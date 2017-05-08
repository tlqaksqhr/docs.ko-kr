---
title: "방법: 격리된 저장소의 기존 파일 및 디렉터리 찾기 | Microsoft Docs"
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
  - "저장소, 파일 및 디렉터리 찾기"
  - "격리된 저장소 파일에서 파일 찾기"
  - "디렉터리[.NET Framework], 격리된 저장소"
  - "격리된 저장소, 파일 및 디렉터리 찾기"
  - "격리된 저장소를 사용하는 데이터 저장소, 파일 및 디렉터리 찾기"
  - "파일[.NET Framework], 격리된 저장소"
  - "데이터 저장소, 파일 및 디렉터리 찾기"
  - "격리된 저장소 파일에서 디렉터리 찾기"
  - "격리된 저장소를 사용하여 데이터 저장, 파일 및 디렉터리 찾기"
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 격리된 저장소의 기존 파일 및 디렉터리 찾기
격리 된 저장소에서 디렉터리 검색을 위해, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=fullName> 메서드를 사용합니다.  이 메서드는 검색 패턴을 나타내는 문자열입니다.  검색 패턴에서 단일 문자\(?\) 및 여러 문자 \(\*\) 와일드카드 문자를 모두 사용할 수 있지만, 와일드 카드 문자는 이름의 마지막 부분에 표시 되어야 합니다.  예를 들어, `directory1/*ect*` 는 올바른 검색 문자열 이지만 `*ect*/directory2` 올바르지 않습니다.  
  
 파일을 검색하기 위해, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=fullName>방법을 사용합니다.  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> 에 적용되는 검색 문자열의 와일드카드 문자 제한 사항이 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> 에도 똑같이 적용됩니다.  
  
 이 방법은 둘다 재귀적입니다. <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 클래스는 나열 하는 모든 디렉터리 또는 파일 저장소에 대한 메서드를 제공 하지 않습니다.  그러나, 재귀 메서드는 다음 코드 예제에 표시 됩니다.  
  
## 예제  
 다음 코드 예제에서는 격리된 저장소에서 파일과 디렉터리를 만드는 방법을 보여 줍니다.  먼저 사용자, 도메인 및 어셈블리별로 격리된 저장소를 검색하여 `isoStore` 변수에 대입합니다.  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> 메서드는 몇 개의 디렉터리를 설정하는 데 사용되고, <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> 생성자는 이러한 디렉토리에 몇 개의 파일을 만듭니다.  그런 다음 코드는 `GetAllDirectories` 메서드 결과를 반복합니다.  이 메서드는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> 를 사용하여 현재 디렉터리에서 모든 디렉터리 이름을 찾습니다.  이러한 이름이 배열로 저장된 다음 `GetAllDirectories` 는 찾은 각 디렉터리를 전달하기 위해 자신을 호출합니다.  결과적으로, 모든 디렉터리 이름은 배열에 반환됩니다.  그런 다음 코드는 `GetAllFiles` 메서드를 호출합니다.  이 메서드는 `GetAllDirectories`를 호출하여 모든 디렉터리의 이름을 확인한 다음 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> 메서드를 사용하여 각 디렉터리를 검사하여 파일을 확인합니다.  결과는 배열로 반환됩니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## 참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)