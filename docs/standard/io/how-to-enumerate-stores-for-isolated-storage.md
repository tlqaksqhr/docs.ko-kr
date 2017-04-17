---
title: "방법: 격리된 저장소의 저장소 열거 | Microsoft Docs"
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
  - "저장소 열거"
  - "격리된 저장소를 사용하는 데이터 저장소, 저장소 열거"
  - "격리된 저장소를 사용하여 데이터 저장, 저장소 열거"
  - "저장소, 열거"
  - "격리된 저장소, 저장소 열거"
  - "데이터 저장소, 열거"
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 격리된 저장소의 저장소 열거
<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=fullName> 정적 메서드를 사용하여 현재 사용자에 대한 모든 격리된 저장소를 열거할 수 있습니다.  이 메서드는 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 값을 받아 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 열거자를 반환 합니다.  저장소를 열거하려면 <xref:System.Security.Permissions.IsolatedStorageFilePermission> 권한을 가지고 있어야 합니다. 이 권한은 <xref:System.Security.Permissions.IsolatedStorageContainment> 값을 지정하는 권한입니다.  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 메서드를 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 값으로 호출할 때, 현재 사용자를 위해 정의 된 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체의 배열을 반환 합니다.  
  
## 예제  
 다음 코드 예제에는 사용자 및 어셈블리 별로 격리된 몇 개의 파일을 만들고 해당 파일을 사용하여 검색된 저장소를 가져오는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 메서드가 있습니다.  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## 참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)