---
title: "격리 유형"
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
- storing data using isolated storage, accessing isolated storage
- storing data using isolated storage, isolation types
- authentication [.NET Framework], isolated storage
- assemblies [.NET Framework], identity
- isolated storage, accessing
- data storage using isolated storage, isolation types
- data storage using isolated storage, accessing isolated storage
- domain identity
- isolated storage, types
- user authentication, isolated storage
ms.assetid: 14812988-473f-44ae-b75f-fd5c2f21fb7b
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6b07c090a381925f5330a820214126a121d3790b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="types-of-isolation"></a>격리 유형
격리 된 저장소에 대 한 액세스는 항상 만든 사용자로 제한 합니다. 이러한 종류의 격리를 구현 하려면 공용 언어 런타임에서 사용 동일한 개념 운영 체제에서 인식 하는 사용자 id의 저장소를 열 때 코드가 실행 되는 프로세스와 관련 된 id 합니다. 이 id는 인증 된 사용자 id, 이지만 가장 동적으로 변경 하려면 현재 사용자의 id를 발생할 수 있습니다.  
  
 격리 된 저장소에 대 한 액세스를 어셈블리 또는 응용 프로그램의 도메인 및 어셈블리와 관련 된 id에 따라 제한 된 이기도 합니다. 런타임은 다음과 같은 방법으로 이러한 id를 얻습니다.  
  
-   도메인 id는 웹 응용 프로그램의 경우 전체 URL을 될 수 있는 응용 프로그램의 증거를 나타냅니다. 도메인 id 셸 호스팅 코드에 대 한 응용 프로그램 디렉터리 경로 기준이 될 수 있습니다. 예를 들어 실행 파일 경로 C:\Office\MyApp.exe 실행 하는 경우 도메인 id는 C:\Office\MyApp.exe 것입니다.  
  
-   어셈블리 id는 어셈블리의 증명 정보입니다. 이 어셈블리의 될 수 있는 암호화 디지털 서명에서 가져올 수 있습니다 [강력한 이름](../../../docs/framework/app-domains/strong-named-assemblies.md), 어셈블리 또는 URL id의 소프트웨어 게시자입니다. 어셈블리에 강력한 이름을 소프트웨어 게시자 id가 있는 경우 소프트웨어 게시자 id가 사용 됩니다. 어셈블리는 인터넷에서 제공 하 고 서명 되지 않은, URL id ´ ù. 어셈블리와 강력한 이름에 대 한 자세한 내용은 참조 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)합니다.  
  
-   로밍 저장소는 로밍 사용자 프로필이 있는 사용자와 함께 이동 합니다. 파일은 네트워크 디렉터리에 기록 하 고 사용자가 로그인 하는 모든 컴퓨터에 다운로드 됩니다. 로밍 사용자 프로필에 대 한 자세한 내용은 참조 하십시오. <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>합니다.  
  
 사용자, 도메인 및 어셈블리 id의 개념을 결합 함으로써 격리 된 저장소 사용 시나리오에 각각 다음과 같은 방법으로 데이터를 격리할 수 있습니다.:  
  
-   [사용자 및 어셈블리별 격리](#UserAssembly)  
  
-   [사용자, 도메인 및 어셈블리별 격리](#UserDomainAssembly)  
  
 이러한 격리 중 하나는 로밍 사용자 프로필과 함께 결합할 수 있습니다. 자세한 내용은 섹션을 참조 하십시오. [격리 된 저장소와 로밍](#Roaming)합니다.  
  
 다음 그림에서는 다른 범위에 있는 저장소는 격리 하는 방법을 보여 줍니다.  
  
 ![사용자 및 어셈블리별 격리](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")  
격리 된 저장소 유형  
  
 로밍 저장소를 제외 하 고 격리 된 저장소는 항상 암시적으로 격리 컴퓨터에서 해당된 컴퓨터에 로컬로 사용 되는 저장소 기능을 사용 하기 때문에 note 합니다.  
  
> [!IMPORTANT]
>  [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램에는 격리된 저장소를 사용할 수 없습니다. 대신에 `Windows.Storage` API에 포함된 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 네임스페이스의 응용 프로그램 데이터 클래스를 사용하여 로컬 데이터 및 파일을 저장합니다. 자세한 내용은 Windows 개발자 센터에서 [응용 프로그램 데이터](http://go.microsoft.com/fwlink/?LinkId=229175) 를 참조하세요.  
  
<a name="UserAssembly"></a>   
## <a name="isolation-by-user-and-assembly"></a>사용자 및 어셈블리별 격리  
 때 데이터를 사용 하는 어셈블리 저장소 사용자 및 어셈블리별 격리는 적절 한 모든 응용 프로그램 도메인에서 액세스할 수 있어야 합니다. 일반적으로이 경우 격리 된 저장소는 여러 응용 프로그램에서 적용 되는 사용자의 이름 또는 라이선스 정보 같은 특정 응용 프로그램에 연결 되지 않은 데이터를 저장할 사용 됩니다. 사용자 및 어셈블리 별로 격리 된 저장소에 액세스 하려면 코드를 응용 프로그램 간에 정보를 전송 트러스트 되어야 합니다. 일반적으로 인트라넷에서 인터넷에는 없지만 사용자 및 어셈블리별 격리 허용 됩니다. 정적 호출 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType> 메서드 및 사용자 및 어셈블리에 전달을 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 이러한 종류의 격리를 사용 하 여 저장소를 반환 합니다.  
  
 다음 코드 예제에서는 사용자 및 어셈블리 별로 격리 된 저장소를 검색 합니다. 스토어를 통해 액세스할 수는 `isoFile` 개체입니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 증명 정보 매개 변수를 사용 하는 예제를 참조 하십시오. <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>합니다.  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> 다음 코드 예제에 나와 있는 것 처럼 메서드는를 사용할 수 있습니다. 이 바로 가기이 키를 사용 하 여 로밍; 수 있는 저장소를 열 수 없습니다. 사용 하 여 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 이러한 경우에 합니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>   
## <a name="isolation-by-user-domain-and-assembly"></a>사용자, 도메인 및 어셈블리별 격리  
 응용 프로그램에서 개인 데이터 저장소를 필요로 하는 타사 어셈블리를 사용 하는 경우에 개인 데이터를 저장 하려면 격리 된 저장소를 사용할 수 있습니다. 만 지정된 된 어셈블리의 코드는 데이터에 액세스할 수 있습니다 및 어셈블리 저장소를 만들 때 실행 중이 던 응용 프로그램에서 어셈블리를 사용 하는 경우에와 저장소를 만든 사용자가을 실행 하는 경우에 사용자, 도메인 및 어셈블리별 격리 보장 하는  응용 프로그램입니다. 사용자, 도메인 및 어셈블리별 격리 타사 어셈블리를 다른 응용 프로그램 데이터 누출 되지 않도록 유지 합니다. 이 격리 유형을 알고 격리 된 저장소를 사용 하려면 있지만 확실 하지 않은 격리를 사용 하 여 어떤 유형의 경우 기본으로 선택 해야 합니다. 정적 호출 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 방식의 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 사용자, 도메인 및 어셈블리를 전달 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 이러한 종류의 격리를 사용 하 여 저장소를 반환 합니다.  
  
 다음 코드 예제에서는 사용자, 도메인 및 어셈블리 별로 격리 된 저장소를 검색 합니다. 스토어를 통해 액세스할 수는 `isoFile` 개체입니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 또 다른 방법은 다음 코드 예제에 나와 있는 것 처럼를 사용할 수 있습니다. 이 바로 가기이 키를 사용 하 여 로밍; 수 있는 저장소를 열 수 없습니다. 사용 하 여 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 이러한 경우에 합니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>   
## <a name="isolated-storage-and-roaming"></a>격리된 저장소 및 로밍  
 로밍 사용자 프로필은 사용자의 id에는 네트워크를 설정 하 고 해당 id를 사용 하 여 모든 개인 설정 된 설정 중단점이 모든 네트워크 컴퓨터에 로그인 할 수 있도록 하는 Windows 기능입니다. 격리 된 저장소를 사용 하는 어셈블리는 사용자의 격리 된 저장소는 로밍 사용자 프로필과 함께 이동 해야 지정할 수 있습니다. 로밍 용도와 함께 사용자 및 어셈블리별 격리 또는 격리로 사용자, 도메인 및 어셈블리별 합니다. 로밍 범위가 사용 하지 않는 경우 로밍 사용자 프로필을 사용 하는 경우에 저장소 이동 되지 않습니다.  
  
 다음 코드 예제에서는 사용자 및 어셈블리 별로 격리 된 로밍 저장소를 검색 합니다. 스토어를 통해 액세스할 수는 `isoFile` 개체입니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 도메인 범위는 로밍 사용자, 도메인 및 응용 프로그램 별로 격리 된 저장소를 추가할 수 있습니다. 다음 코드 예제에서는이 보여 줍니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)
