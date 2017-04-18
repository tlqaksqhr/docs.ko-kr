---
title: "방법: 격리된 저장소의 저장소 가져오기 | Microsoft Docs"
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
  - "저장소, 가져오기"
  - "격리된 저장소를 사용하여 데이터 저장, 저장소 가져오기"
  - "격리된 저장소, 저장소 가져오기"
  - "데이터 저장소, 가져오기"
  - "격리된 저장소를 사용하는 데이터 저장소, 저장소 가져오기"
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
caps.latest.revision: 19
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: 격리된 저장소의 저장소 가져오기
격리된 저장소는 데이터 컴파트먼트 내에서 가상 파일 시스템을 노출합니다.  <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 클래스는 격리된 저장소와 상호 작용 하기 위한 메서드를 제공 합니다.  저장소를 만들고 검색하기 위해 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>은 세 가지 정적 메서드를 제공합니다.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>를 호출하면 사용자와 어셈블리별로 격리된 저장소가 반환됩니다.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>을 호출하면 도메인과 어셈블리별로 격리된 저장소가 반환됩니다.  
  
     이 두 메서드는 모두 자신이 호출되는 코드 블록에 속하는 저장소를 검색합니다.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 정적 메서드는 범위 매개 변수 조합을 전달하여 지정되는 격리된 저장소를 반환합니다.  
  
 다음 코드 예제에서는 사용자, 도메인 및 어셈블로별로 격리된 저장소를 반환니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드를 사용하여 로밍 사용자 프로필과 함께 저장소를 로밍하도록 지정할 수 있습니다.  이를 설정하는 방법에 대한 자세한 내용은 [격리 유형](../../../docs/standard/io/types-of-isolation.md)를 참조하십시오.  
  
 다른 어셈블리 내에서 가져온 격리된 저장소는 기본적으로 서로 다릅니다.  어셈블리 또는 도메인 증명을 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드의 마지막 두 매개 변수로서 전달하여 다른 어셈블리 또는 도메인의 저장소에 액세스할 수 있습니다.  이렇게 하려면 응용 프로그램 도메인 ID로 격리된 저장소에 액세스할 수 있는 권한이 필요합니다.  자세한 내용은 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드 오버로드를 참조하십시오.  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, 및<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>개체를 반환합니다.  어떤 격리 유형을 사용하는 것이 가장 적절한지를 결정하려면 [격리 유형](../../../docs/standard/io/types-of-isolation.md)을 참조하십시오.  격리된 저장소 파일 개체를 가지고 있을 떄, 격리된 저장소 메서드를 사용하여 파일과 파일 디렉터리 읽기, 쓰기, 만들기 및 삭제 작업을 수행할 수 있습니다.  
  
 코드가 저장소 자체를 가져올 수 있는 권한이 없는 코드에 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체를 전달하지 못하도록 하는 메커니즘은 없습니다.  도메인과 어셈블리 ID 및 격리된 저장소 권한은 일반적으로 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> 또는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드에서 <xref:System.IO.IsolatedStorage.IsolatedStorage> 개체에 대한 참조를 가져오는 경우에만 검사합니다.  따라서 이러한 참조를 사용하는 코드는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체에 대한 참조를 보호해야 합니다.  
  
## 예제  
 다음 코드 예제는 사용자 및 어셈블리별로 격리된 저장소를 가져오는 클래스에 대한 간단한 예제를 제공합니다.  이 코드는 사용자, 도메인, 및 어셈블리별로 격리된 저장소를 <xref:System.IO.IsolatedStorage.IsolatedStorageScope?displayProperty=fullName>를 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>메서드가 전달하는 인수에 추가하여 검색하도록 변경할 수 있습니다.  
  
 코드를 실행한 후, 명령줄에 **StoreAdm \/LIST**를 입력하여 저장소가 만들어졌는지 확인할 수 있습니다.  이것은 [Isolated Storage tool \(Storeadm.exe\)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md)를 실행하고 사용자에게 현재 격리된 저장소가 모두 나열됩니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## 참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>   
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)   
 [격리 유형](../../../docs/standard/io/types-of-isolation.md)   
 [공용 언어 런타임의 어셈블리](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)