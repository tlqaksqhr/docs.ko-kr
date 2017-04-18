---
title: "방법: 격리된 저장소의 공간 부족 상태 예상 | Microsoft Docs"
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
  - "데이터 저장소, 할당량"
  - "격리된 저장소, 할당량"
  - "격리된 저장소 사용 크기"
  - "격리된 저장소 사용 제한"
  - "저장소, 할당량"
  - "저장소, 공간 부족 조건"
  - "격리된 저장소를 사용하는 데이터 저장소, 할당량"
  - "격리된 저장소를 사용하여 데이터 저장, 할당량"
  - "격리된 저장소에 남은 공간"
  - "데이터 저장소, 공간 부족 조건"
  - "격리된 저장소를 사용하여 데이터 저장, 공간 부족 조건"
  - "격리된 저장소의 할당량"
  - "격리된 저장소, 공간 부족 조건"
  - "격리된 저장소를 사용하는 데이터 저장소, 공간 부족 조건"
ms.assetid: e35d4535-3732-421e-b1a3-37412e036145
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: 격리된 저장소의 공간 부족 상태 예상
격리된 저장소를 사용하는 코드는 격리된 저장소 파일과 디렉터리가 있는 데이터 컴파트먼트의 최대 크기를 지정하는 [할당 한도](../../../docs/standard/io/isolated-storage.md#quotas)의 제약을 받습니다.  이 비율은 보안 정책에서 정의하고 관리자가 구성할 수 있습니다.  데이터를 쓰고 싶을 때 최대 허용 크기를 초과하면 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 예외가 throw되고 작업이 실패합니다.  이렇게 되면 데이터 저장소가 꽉 차서 응용 프로그램이 요청을 거부할 수 있는 악성 서비스 거부 공격 문제를 방지할 수 있습니다.  
  
 이런 이유로 인해 지정된 쓰기 작업이 실패할 수 있는지 여부를 판단할 수 있도록 <xref:System.IO.IsolatedStorage.IsolatedStorage> 클래스는 <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A> 및 <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>라는 세 가지 읽기 전용 속성을 제공합니다.  이러한 속성을 사용하면 저장소에 쓰는 작업으로 인해 저장소의 최대 허용 크기가 초과되는지 여부를 판단할 수 있습니다.  이 속성을 사용할 때는 격리된 저장소에 동시에 액세스할 수 있음을 명심하십시오. 따라서 남은 저장소 크기를 계산하는 경우 저장소에 쓰는 시간에 따라 저장소 공간이 사용될 수 있습니다.  그러나 사용 가능한 저장소의 상한값에 도달하는지 여부를 판단하기 위해 저장소의 최대 크기를 사용할 수는 있습니다.  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> 속성이 제대로 동작 하려면 어셈블리 증명 정보에 따라 달라 집니다.  따라서 이 속성은 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, 또는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드를 사용하여 만들어진 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>개체에서만 검색되어야 합니다.  다른 방법 \(예를 들어 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 메서드\) 에서 만들어진 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체는 정확한 최대 크기를 반환하지 않습니다.  
  
## 예제  
 다음 코드 예제에서는 격리된 저장소를 가져오고, 몇 개의 파일을 만든 다음 <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> 속성을 검색합니다.  남은 공간은 바이트 단위로 보고됩니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## 참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)   
 [방법: 격리된 저장소의 저장소 가져오기](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)