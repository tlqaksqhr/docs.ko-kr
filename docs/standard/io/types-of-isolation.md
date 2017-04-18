---
title: "격리 유형 | Microsoft Docs"
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
  - "격리된 저장소를 사용하여 데이터 저장, 격리된 저장소 액세스"
  - "격리된 저장소를 사용하여 데이터 저장, 격리 형식"
  - "인증[.NET Framework], 격리된 저장소"
  - "어셈블리[.NET Framework], ID"
  - "격리된 저장소, 액세스"
  - "격리된 저장소를 사용하는 데이터 저장소, 격리 형식"
  - "격리된 저장소를 사용하는 데이터 저장소, 격리된 저장소 액세스"
  - "도메인 ID"
  - "격리된 저장소, 형식"
  - "사용자 인증, 격리된 저장소"
ms.assetid: 14812988-473f-44ae-b75f-fd5c2f21fb7b
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# 격리 유형
격리된 저장소를 만든 사용자만 해당 저장소에 액세스할 수 있습니다.  이런 유형의 격리를 구현하기 위해 공용 언어 런타임은 운영 체제에서 인식하는 사용자 ID에 대한 동일한 개념을 사용합니다. 이것은 저장소를 열 때 코드가 실행 중인 프로세스와 연관된 ID입니다.  이 ID는 인증된 사용자 ID이지만 가장으로 인해 현재 사용자의 ID가 동적으로 변경될 수 있습니다.  
  
 격리된 저장소에 대한 액세스는 또한 응용 프로그램의 도메인과 어셈블리 또는 어셈블리와 관련된 ID에 따라 격리된 저장소에 대해 제한됩니다.  런타임은 다음과 같은 방법으로 이러한 ID를 얻습니다.  
  
-   도메인 ID는 웹 응용 프로그램이 전체 URL인 경우 응용 프로그램의 증명 정보를 나타냅니다.  셸 호스팅 응용 프로그램의 경우 도메인 ID가 응용 프로그램 디렉터리 경로를 기반으로 할 수도 있습니다.  예를 들어, C:\\Office\\MyApp.exe 경로의 실행 파일을 실행하는 경우 도메인 ID는 C:\\Office\\MyApp.exe입니다.  
  
-   어셈블리 ID는 어셈블리의 증명 정보이며   어셈블리의 [강력한 이름](../../../docs/framework/app-domains/strong-named-assemblies.md)이 될 수 있는 암호화 디지털 서명, 어셈블리의 소프트웨어 게시자 또는 URL ID에서 가져올 수 있습니다.  어셈블리에 강력한 이름과 소프트웨어 게시자 ID가 둘 다 있는 경우 소프트웨어 게시자 ID가 사용되며  어셈블리의 출처가 인터넷이고 서명되지 않은 경우 URL ID가 사용됩니다.  어셈블리와 강력한 이름에 대한 자세한 내용은 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)을 참조하십시오.  
  
-   로밍 저장소는 로밍 사용자 프로필을 가진 사용자와 같이 이동합니다.  파일은 네트워크 디렉터리에 쓰여지고 사용자가 로그인하는 컴퓨터에 다운로드됩니다.  로밍 사용자 프로필에 대한 자세한 내용은 <xref:System.IO.IsolatedStorage.IsolatedStorageScope?displayProperty=fullName>을 참조하십시오.  
  
 사용자, 도메인 및 어셈블리 ID 개념을 결합하면 격리된 저장소는 각각 고유한 사용 시나리오를 가지고 있는 다음과 같은 방법으로 데이터를 격리시킬 수 있습니다.  
  
-   [사용자 및 어셈블리별 격리](#UserAssembly)  
  
-   [사용자, 도메인 및 어셈블리별 격리.](#UserDomainAssembly)  
  
 이러한 격리 중 하나를 로밍 사용자 프로필과 함께 사용할 수 있습니다.  자세한 내용은 섹션을 참조 하십시오. [격리 된 저장소와 로밍](#Roaming).  
  
 다음 그림은 저장소가 다양한 범위에서 격리되는 방식을 보여 줍니다.  
  
 ![사용자 및 어셈블리별 격리](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")  
격리된 저장소 유형  
  
 로밍 저장소를 제외한 격리된 저장소는 지정된 컴퓨터 로컬에 있는 저장소 기능을 사용하므로 항상 해당 컴퓨터에 의해 암시적으로 격리됩니다.  
  
> [!IMPORTANT]
>  [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램에서는 격리 된 저장소를 사용할 수 없습니다.  대신에 [!INCLUDE[wrt](../../../includes/wrt-md.md)]에 포함된 `Windows.Storage` 네임 스페이스의 응용 프로그램 데이터 클래스를 사용하여 API 로컬 데이터 및 파일을 저장할 수 있습니다.  자세한 내용은 Windows 개발자 센터에서 [응용 프로그램 데이터](http://go.microsoft.com/fwlink/?LinkId=229175) 을 참조하십시오.  
  
<a name="UserAssembly"></a>   
## 사용자 및 어셈블리별 격리  
 데이터 저장소를 사용하는 어셈블리를 응용 프로그램의 도메인에서 액세스할 수 있어야 하는 경우 사용자 및 어셈블리별 격리 방법이 적절합니다.  이런 경우 일반적으로 격리된 저장소는 여러 응용 프로그램 간에 적용되는 데이터를 저장하는 데 사용되며 사용자 이름 또는 라이센스 정보 등의 특정 응용 프로그램에만 국한되지 않습니다.  사용자 및 어셈블리별로 격리된 저장소에 액세스하려면 응용 프로그램 간에 정보를 전송할 수 있도록 코드가 신뢰를 받아야 합니다.  일반적으로 사용자 및 어셈블리별 격리는 인트라넷에서 허용되지만 인터넷에서는 허용되지 않습니다.  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=fullName> 의 정적메서드를 호출하고 사용자와 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 어셈블리에서 격리 유형의 저장소가 반환됩니다.  
  
 다음 코드 예제에서는 사용자 및 어셈블리별로 격리된 저장소를 검색합니다.  `isoFile` 개체를 통해 저장소에 액세스할 수 있습니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 증명 매개 변수를 사용하는 예제는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29> 를 참조하십시오.  
  
 다음 코드 예제에서와 같이 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> 메서드를 사용하면 이 작업을 더 빨리 수행할 수 있습니다.  이 바로가기는 로밍할 수 있는 저장소를 여는 데는 사용할 수 없으므로 이런 경우에는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>를 사용하십시오.  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>   
## 사용자, 도메인 및 어셈블리별 격리  
 응용 프로그램이 개인 데이터 저장소를 필요로 하는 타사 어셈블리를 사용하는 경우 격리된 저장소를 사용하여 개인 데이터를 저장할 수 있습니다.  사용자, 도메인 및 어셈블리별 격리를 사용하면 지정된 어셈블리의 코드로만 데이터에 액세스할 수 있고, 어셈블리가 저장소를 만들었을 때 실행 중이던 응용 프로그램에서 어셈블리를 사용하는 경우만 그리고 저장소를 만든 사용자가 응용 프로그램을 실행하는 경우만 확인합니다.  사용자, 도메인 및 어셈블리별 격리를 사용하면 타사 어셈블리에서 다른 응용 프로그램에 대한 데이터를 누출시키지 못합니다.  격리된 저장소를 사용하려는 경우 어떤 격리 유형을 사용해야 할지 잘 모르면 사용자, 도메인 및 어셈블리별 격리를 기본으로 선택하십시오.  <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 의 정적 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드를 호출하고 사용자, 도메인 및 어셈블리에서 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 를 전달하면 이러한 격리 유형의 저장소가 반환됩니다.  
  
 다음 코드 예제에서는 사용자, 도메인 및 어셈블로별로 격리된 저장소를 검색합니다.  `isoFile`개체를 통해 저장소에 액세스할 수 있습니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 다음 코드 예제에서와 같이 다른 메서드를 사용하여 더 빨리 수행할 수 있습니다.  이 바로가기는 로밍할 수 있는 저장소를 여는 데는 사용할 수 없으므로 이런 경우에는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 를 사용하십시오.  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>   
## 격리된 저장소 및 로밍  
 로밍 사용자 프로필은 사용자 네트워크 ID를 설정하고 해당 ID를 사용하여 모든 사용자 지정 설정 수행, 모든 네트워크 컴퓨터에 로그인 할 수 있게 해 주는 Windows 기능입니다.  격리된 저장소를 사용하는 어셈블리는 사용자의 격리된 저장소를 로밍 사용자 프로필과 함께 이동하도록 지정할 수 있습니다.  로밍은 사용자 및 어셈블리별 격리 또는 사용자, 도메인 및 어셈블리별 격리와 함께 사용할 수 있습니다.  로밍 범위가 사용되지 않으면 로밍 사용자 프로필이 사용되더라도 저장소를 로밍하지 않습니다.  
  
 다음 코드 예제에서는 사용자 및 어셈블리별로 격리된 로밍 저장소를 검색합니다.  `isoFile` 개체를 통해 저장소에 액세스할 수 있습니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 도메인 범위를 추가하여 사용자, 도메인 및 응용 프로그램별로 격리된 로밍 저장소를 만들 수 있습니다.  다음 코드 예제에서 이를 보여 줍니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## 참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>   
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)