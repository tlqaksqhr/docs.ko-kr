---
title: "방법: 격리된 저장소에서 저장소 삭제 | Microsoft Docs"
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
  - "저장소, 삭제"
  - "데이터 저장소, 삭제"
  - "저장소 삭제"
  - "저장소 제거"
  - "격리된 저장소, 저장소 삭제"
  - "격리된 저장소를 사용하여 데이터 저장, 저장소 삭제"
  - "격리된 저장소를 사용하는 데이터 저장소, 저장소 삭제"
ms.assetid: 3947e333-5af6-4601-b2f1-24d4d6129cf3
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 격리된 저장소에서 저장소 삭제
<xref:System.IO.IsolatedStorage.IsolatedStorageFile> 클래스는 격리된 저장소 파일을 삭제하기 위해 다음과 같은 두 가지 메서드를 제공합니다.  
  
-   인스턴스 메서드 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove>는 인수를 사용하지 않으며 메서드를 호출하는 저장소를 삭제합니다. 사용 권한이 없어도 이 작업을 수행할 수 있습니다. 저장소에 액세스할 수 있는 코드는 저장소 내의 데이터를 일부 또는 모두 삭제할 수 있습니다.  
  
-   정적 메서드 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>는 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 열거형 값을 사용하여 코드를 실행 중인 사용자의 모든 저장소를 삭제합니다. 이 작업을 수행하려면 <xref:System.Security.Permissions.IsolatedStorageFilePermission> 값에 대한 <xref:System.Security.Permissions.IsolatedStorageContainment> 권한이 필요합니다.  
  
## 예제  
 다음 코드 예제에서는 정적 및 인스턴스 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> 메서드를 사용하는 방법을 보여 줍니다. 이 클래스는 사용자 및 어셈블리에 대해 격리된 저장소와 사용자, 도메인 및 어셈블리에 대해 격리된 저장소를 가져옵니다. 그런 다음 격리된 저장소 파일 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove>의 `isoStore1` 메서드를 호출하여 사용자, 도메인 및 어셈블리 저장소를 삭제합니다. 마지막으로 정적 메서드인 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>를 호출하여 사용자에 대한 나머지 저장소를 삭제합니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.IsolatedStorage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source3.cs#3)]
 [!code-vb[Conceptual.IsolatedStorage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source3.vb#3)]  
  
## 참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)