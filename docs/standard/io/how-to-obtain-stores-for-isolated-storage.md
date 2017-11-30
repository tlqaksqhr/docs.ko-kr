---
title: "방법: 격리된 저장소의 저장소 가져오기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, obtaining
- storing data using isolated storage, obtaining stores
- isolated storage, obtaining stores
- data stores, obtaining
- data storage using isolated storage, obtaining stores
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb0b877aa0f4cee36bd1f8c1cea624cf9368fbaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a>방법: 격리된 저장소의 저장소 가져오기
격리된 저장소는 데이터 구획 내에서 가상 파일 시스템을 노출합니다. <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 클래스는 격리된 저장소와 상호 작용하는 데 필요한 여러 가지 메서드를 제공합니다. 저장소를 만들고 검색하기 위해 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>은 세 가지 정적 메서드를 제공합니다.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>는 사용자와 어셈블리별로 격리된 저장소를 반환합니다.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>은 도메인과 어셈블리별로 격리된 저장소를 반환합니다.  
  
     이 두 메서드는 모두 자신이 호출되는 코드에 속하는 저장소를 검색합니다.  
  
-   정적 메서드 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 범위 매개 변수를 조합 하 여 지정 된 격리 된 저장소를 반환 합니다.  
  
 다음 코드는 사용자, 어셈블리 및 도메인별로 격리된 저장소를 반환합니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드를 사용하여 로밍 사용자 프로필과 함께 저장소를 로밍하도록 지정할 수 있습니다. 이 작업을 설정 하는 방법에 대 한 세부 정보를 참조 하십시오. [격리 유형](../../../docs/standard/io/types-of-isolation.md)합니다.  
  
 다른 어셈블리 내에서 가져온 격리 된 저장소는 기본적으로 서로 다른 저장소입니다. 어셈블리 또는 도메인 증명을 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드의 매개 변수에서 전달하여 다른 어셈블리 또는 도메인의 저장소에 액세스할 수 있습니다. 이 응용 프로그램 도메인 id 여 격리 된 저장소에 액세스할 수 있는 권한이 필요 합니다. 자세한 내용은 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드 오버로드를 참조하십시오.  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> 및 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체를 반환합니다. 상황에 가장 적합 한 격리 유형을 결정할 수 있도록, 참조 [격리 유형](../../../docs/standard/io/types-of-isolation.md)합니다. 격리된 저장소 파일 개체가 있으면 격리된 저장소 메서드를 사용하여 파일과 디렉터리를 읽고 쓰고 만들고 삭제하는 작업을 수행할 수 있습니다.  
  
 코드가 저장소 자체를 가져올 수 있는 액세스 권한이 충분하지 않은 코드에 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체를 전달하지 못하도록 하는 메커니즘은 없습니다. 경우에 대 한 참조에만 도메인 및 어셈블리 id와 격리 된 저장소 사용 권한을 검사는 <xref:System.IO.IsolatedStorage.IsolatedStorage> 개체를 얻은 일반적으로 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, 또는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드. 에 대 한 참조를 보호 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체 즉, 이러한 참조를 사용 하는 코드의 책임입니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 사용자 및 어셈블리별로 격리된 저장소를 가져오는 클래스의 간단한 예제를 제공합니다. <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> 메서드가 전달하는 인수에 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>을 추가하면 사용자, 도메인 및 어셈블리별로 격리된 저장소를 검색하도록 코드를 변경할 수 있습니다.  
  
 코드를 실행 한 후 저장소를 입력 하 여 만들어졌는지 확인할 수 있습니다 **StoreAdm /LIST** 명령줄에서. 이 실행 되는 [격리 된 저장소 도구 (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) 현재 격리 된 사용자에 대 한 저장소가 모두 나열 합니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)  
 [격리 유형](../../../docs/standard/io/types-of-isolation.md)  
 [공용 언어 런타임의 어셈블리](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
