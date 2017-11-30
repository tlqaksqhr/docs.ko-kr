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
# <a name="types-of-isolation"></a><span data-ttu-id="9ad82-102">격리 유형</span><span class="sxs-lookup"><span data-stu-id="9ad82-102">Types of Isolation</span></span>
<span data-ttu-id="9ad82-103">격리 된 저장소에 대 한 액세스는 항상 만든 사용자로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-103">Access to isolated storage is always restricted to the user who created it.</span></span> <span data-ttu-id="9ad82-104">이러한 종류의 격리를 구현 하려면 공용 언어 런타임에서 사용 동일한 개념 운영 체제에서 인식 하는 사용자 id의 저장소를 열 때 코드가 실행 되는 프로세스와 관련 된 id 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-104">To implement this type of isolation, the common language runtime uses the same notion of user identity that the operating system recognizes, which is the identity associated with the process in which the code is running when the store is opened.</span></span> <span data-ttu-id="9ad82-105">이 id는 인증 된 사용자 id, 이지만 가장 동적으로 변경 하려면 현재 사용자의 id를 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-105">This identity is an authenticated user identity, but impersonation can cause the identity of the current user to change dynamically.</span></span>  
  
 <span data-ttu-id="9ad82-106">격리 된 저장소에 대 한 액세스를 어셈블리 또는 응용 프로그램의 도메인 및 어셈블리와 관련 된 id에 따라 제한 된 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-106">Access to isolated storage is also restricted according to the identity associated with the application's domain and assembly, or with the assembly alone.</span></span> <span data-ttu-id="9ad82-107">런타임은 다음과 같은 방법으로 이러한 id를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-107">The runtime obtains these identities in the following ways:</span></span>  
  
-   <span data-ttu-id="9ad82-108">도메인 id는 웹 응용 프로그램의 경우 전체 URL을 될 수 있는 응용 프로그램의 증거를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-108">Domain identity represents the evidence of the application, which in the case of a web application might be the full URL.</span></span> <span data-ttu-id="9ad82-109">도메인 id 셸 호스팅 코드에 대 한 응용 프로그램 디렉터리 경로 기준이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-109">For shell-hosted code, the domain identity might be based on the application directory path.</span></span> <span data-ttu-id="9ad82-110">예를 들어 실행 파일 경로 C:\Office\MyApp.exe 실행 하는 경우 도메인 id는 C:\Office\MyApp.exe 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-110">For example, if the executable runs from the path C:\Office\MyApp.exe, the domain identity would be C:\Office\MyApp.exe.</span></span>  
  
-   <span data-ttu-id="9ad82-111">어셈블리 id는 어셈블리의 증명 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-111">Assembly identity is the evidence of the assembly.</span></span> <span data-ttu-id="9ad82-112">이 어셈블리의 될 수 있는 암호화 디지털 서명에서 가져올 수 있습니다 [강력한 이름](../../../docs/framework/app-domains/strong-named-assemblies.md), 어셈블리 또는 URL id의 소프트웨어 게시자입니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-112">This might come from a cryptographic digital signature, which can be the assembly's [strong name](../../../docs/framework/app-domains/strong-named-assemblies.md), the software publisher of the assembly, or its URL identity.</span></span> <span data-ttu-id="9ad82-113">어셈블리에 강력한 이름을 소프트웨어 게시자 id가 있는 경우 소프트웨어 게시자 id가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-113">If an assembly has both a strong name and a software publisher identity, then the software publisher identity is used.</span></span> <span data-ttu-id="9ad82-114">어셈블리는 인터넷에서 제공 하 고 서명 되지 않은, URL id ´ ù.</span><span class="sxs-lookup"><span data-stu-id="9ad82-114">If the assembly comes from the Internet and is unsigned, the URL identity is used.</span></span> <span data-ttu-id="9ad82-115">어셈블리와 강력한 이름에 대 한 자세한 내용은 참조 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-115">For more information about assemblies and strong names, see [Programming with Assemblies](../../../docs/framework/app-domains/programming-with-assemblies.md).</span></span>  
  
-   <span data-ttu-id="9ad82-116">로밍 저장소는 로밍 사용자 프로필이 있는 사용자와 함께 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-116">Roaming stores move with a user that has a roaming user profile.</span></span> <span data-ttu-id="9ad82-117">파일은 네트워크 디렉터리에 기록 하 고 사용자가 로그인 하는 모든 컴퓨터에 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-117">Files are written to a network directory and are downloaded to any computer the user logs into.</span></span> <span data-ttu-id="9ad82-118">로밍 사용자 프로필에 대 한 자세한 내용은 참조 하십시오. <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-118">For more information about roaming user profiles, see <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="9ad82-119">사용자, 도메인 및 어셈블리 id의 개념을 결합 함으로써 격리 된 저장소 사용 시나리오에 각각 다음과 같은 방법으로 데이터를 격리할 수 있습니다.:</span><span class="sxs-lookup"><span data-stu-id="9ad82-119">By combining the concepts of user, domain, and assembly identity, isolated storage can isolate data in the following ways, each of which has its own usage scenarios:</span></span>  
  
-   [<span data-ttu-id="9ad82-120">사용자 및 어셈블리별 격리</span><span class="sxs-lookup"><span data-stu-id="9ad82-120">Isolation by user and assembly</span></span>](#UserAssembly)  
  
-   [<span data-ttu-id="9ad82-121">사용자, 도메인 및 어셈블리별 격리</span><span class="sxs-lookup"><span data-stu-id="9ad82-121">Isolation by user, domain, and assembly</span></span>](#UserDomainAssembly)  
  
 <span data-ttu-id="9ad82-122">이러한 격리 중 하나는 로밍 사용자 프로필과 함께 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-122">Either of these isolations can be combined with a roaming user profile.</span></span> <span data-ttu-id="9ad82-123">자세한 내용은 섹션을 참조 하십시오. [격리 된 저장소와 로밍](#Roaming)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-123">For more information, see the section [Isolated Storage and Roaming](#Roaming).</span></span>  
  
 <span data-ttu-id="9ad82-124">다음 그림에서는 다른 범위에 있는 저장소는 격리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-124">The following illustration demonstrates how stores are isolated in different scopes.</span></span>  
  
 <span data-ttu-id="9ad82-125">![사용자 및 어셈블리별 격리](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")</span><span class="sxs-lookup"><span data-stu-id="9ad82-125">![Isolation by user and assembly](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")</span></span>  
<span data-ttu-id="9ad82-126">격리 된 저장소 유형</span><span class="sxs-lookup"><span data-stu-id="9ad82-126">Types of isolated storage</span></span>  
  
 <span data-ttu-id="9ad82-127">로밍 저장소를 제외 하 고 격리 된 저장소는 항상 암시적으로 격리 컴퓨터에서 해당된 컴퓨터에 로컬로 사용 되는 저장소 기능을 사용 하기 때문에 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-127">Note that except for roaming stores, isolated storage is always implicitly isolated by computer because it uses the storage facilities that are local to a given computer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9ad82-128">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램에는 격리된 저장소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-128">Isolated storage is not available for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="9ad82-129">대신에 `Windows.Storage` API에 포함된 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 네임스페이스의 응용 프로그램 데이터 클래스를 사용하여 로컬 데이터 및 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-129">Instead, use the application data classes in the `Windows.Storage` namespaces included in the [!INCLUDE[wrt](../../../includes/wrt-md.md)] API to store local data and files.</span></span> <span data-ttu-id="9ad82-130">자세한 내용은 Windows 개발자 센터에서 [응용 프로그램 데이터](http://go.microsoft.com/fwlink/?LinkId=229175) 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ad82-130">For more information, see [Application data](http://go.microsoft.com/fwlink/?LinkId=229175) in the Windows Dev Center.</span></span>  
  
<a name="UserAssembly"></a>   
## <a name="isolation-by-user-and-assembly"></a><span data-ttu-id="9ad82-131">사용자 및 어셈블리별 격리</span><span class="sxs-lookup"><span data-stu-id="9ad82-131">Isolation by User and Assembly</span></span>  
 <span data-ttu-id="9ad82-132">때 데이터를 사용 하는 어셈블리 저장소 사용자 및 어셈블리별 격리는 적절 한 모든 응용 프로그램 도메인에서 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-132">When the assembly that uses the data store needs to be accessible from any application's domain, isolation by user and assembly is appropriate.</span></span> <span data-ttu-id="9ad82-133">일반적으로이 경우 격리 된 저장소는 여러 응용 프로그램에서 적용 되는 사용자의 이름 또는 라이선스 정보 같은 특정 응용 프로그램에 연결 되지 않은 데이터를 저장할 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-133">Typically, in this situation, isolated storage is used to store data that applies across multiple applications and is not tied to any particular application, such as the user's name or license information.</span></span> <span data-ttu-id="9ad82-134">사용자 및 어셈블리 별로 격리 된 저장소에 액세스 하려면 코드를 응용 프로그램 간에 정보를 전송 트러스트 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-134">To access storage isolated by user and assembly, code must be trusted to transfer information between applications.</span></span> <span data-ttu-id="9ad82-135">일반적으로 인트라넷에서 인터넷에는 없지만 사용자 및 어셈블리별 격리 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-135">Typically, isolation by user and assembly is allowed on intranets but not on the Internet.</span></span> <span data-ttu-id="9ad82-136">정적 호출 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType> 메서드 및 사용자 및 어셈블리에 전달을 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 이러한 종류의 격리를 사용 하 여 저장소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-136">Calling the static <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType> method and passing in a user and an assembly <xref:System.IO.IsolatedStorage.IsolatedStorageScope> returns storage with this kind of isolation.</span></span>  
  
 <span data-ttu-id="9ad82-137">다음 코드 예제에서는 사용자 및 어셈블리 별로 격리 된 저장소를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-137">The following code example retrieves a store that is isolated by user and assembly.</span></span> <span data-ttu-id="9ad82-138">스토어를 통해 액세스할 수는 `isoFile` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-138">The store can be accessed through the `isoFile` object.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 <span data-ttu-id="9ad82-139">증명 정보 매개 변수를 사용 하는 예제를 참조 하십시오. <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-139">For an example that uses the evidence parameters, see <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.</span></span>  
  
 <span data-ttu-id="9ad82-140"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> 다음 코드 예제에 나와 있는 것 처럼 메서드는를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-140">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> method is available as a shortcut, as shown in the following code example.</span></span> <span data-ttu-id="9ad82-141">이 바로 가기이 키를 사용 하 여 로밍; 수 있는 저장소를 열 수 없습니다. 사용 하 여 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 이러한 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-141">This shortcut cannot be used to open stores that are capable of roaming; use <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> in such cases.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>   
## <a name="isolation-by-user-domain-and-assembly"></a><span data-ttu-id="9ad82-142">사용자, 도메인 및 어셈블리별 격리</span><span class="sxs-lookup"><span data-stu-id="9ad82-142">Isolation by User, Domain, and Assembly</span></span>  
 <span data-ttu-id="9ad82-143">응용 프로그램에서 개인 데이터 저장소를 필요로 하는 타사 어셈블리를 사용 하는 경우에 개인 데이터를 저장 하려면 격리 된 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-143">If your application uses a third-party assembly that requires a private data store, you can use isolated storage to store the private data.</span></span> <span data-ttu-id="9ad82-144">만 지정된 된 어셈블리의 코드는 데이터에 액세스할 수 있습니다 및 어셈블리 저장소를 만들 때 실행 중이 던 응용 프로그램에서 어셈블리를 사용 하는 경우에와 저장소를 만든 사용자가을 실행 하는 경우에 사용자, 도메인 및 어셈블리별 격리 보장 하는  응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-144">Isolation by user, domain, and assembly ensures that only code in a given assembly can access the data, and only when the assembly is used by the application that was running when the assembly created the store, and only when the user for whom the store was created runs the application.</span></span> <span data-ttu-id="9ad82-145">사용자, 도메인 및 어셈블리별 격리 타사 어셈블리를 다른 응용 프로그램 데이터 누출 되지 않도록 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-145">Isolation by user, domain, and assembly keeps the third-party assembly from leaking data to other applications.</span></span> <span data-ttu-id="9ad82-146">이 격리 유형을 알고 격리 된 저장소를 사용 하려면 있지만 확실 하지 않은 격리를 사용 하 여 어떤 유형의 경우 기본으로 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-146">This isolation type should be your default choice if you know that you want to use isolated storage but are not sure which type of isolation to use.</span></span> <span data-ttu-id="9ad82-147">정적 호출 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 방식의 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 사용자, 도메인 및 어셈블리를 전달 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 이러한 종류의 격리를 사용 하 여 저장소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-147">Calling the static <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method of <xref:System.IO.IsolatedStorage.IsolatedStorageFile> and passing in a user, domain, and assembly <xref:System.IO.IsolatedStorage.IsolatedStorageScope> returns storage with this kind of isolation.</span></span>  
  
 <span data-ttu-id="9ad82-148">다음 코드 예제에서는 사용자, 도메인 및 어셈블리 별로 격리 된 저장소를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-148">The following code example retrieves a store isolated by user, domain, and assembly.</span></span> <span data-ttu-id="9ad82-149">스토어를 통해 액세스할 수는 `isoFile` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-149">The store can be accessed through the `isoFile` object.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 <span data-ttu-id="9ad82-150">또 다른 방법은 다음 코드 예제에 나와 있는 것 처럼를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-150">Another method is available as a shortcut, as shown in the following code example.</span></span> <span data-ttu-id="9ad82-151">이 바로 가기이 키를 사용 하 여 로밍; 수 있는 저장소를 열 수 없습니다. 사용 하 여 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 이러한 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-151">This shortcut cannot be used to open stores that are capable of roaming; use <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> in such cases.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>   
## <a name="isolated-storage-and-roaming"></a><span data-ttu-id="9ad82-152">격리된 저장소 및 로밍</span><span class="sxs-lookup"><span data-stu-id="9ad82-152">Isolated Storage and Roaming</span></span>  
 <span data-ttu-id="9ad82-153">로밍 사용자 프로필은 사용자의 id에는 네트워크를 설정 하 고 해당 id를 사용 하 여 모든 개인 설정 된 설정 중단점이 모든 네트워크 컴퓨터에 로그인 할 수 있도록 하는 Windows 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-153">Roaming user profiles are a Windows feature that enables a user to set up an identity on a network and use that identity to log into any network computer, carrying over all personalized settings.</span></span> <span data-ttu-id="9ad82-154">격리 된 저장소를 사용 하는 어셈블리는 사용자의 격리 된 저장소는 로밍 사용자 프로필과 함께 이동 해야 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-154">An assembly that uses isolated storage can specify that the user's isolated storage should move with the roaming user profile.</span></span> <span data-ttu-id="9ad82-155">로밍 용도와 함께 사용자 및 어셈블리별 격리 또는 격리로 사용자, 도메인 및 어셈블리별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-155">Roaming can be used in conjunction with isolation by user and assembly or with isolation by user, domain, and assembly.</span></span> <span data-ttu-id="9ad82-156">로밍 범위가 사용 하지 않는 경우 로밍 사용자 프로필을 사용 하는 경우에 저장소 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-156">If a roaming scope is not used, stores will not roam even if a roaming user profile is used.</span></span>  
  
 <span data-ttu-id="9ad82-157">다음 코드 예제에서는 사용자 및 어셈블리 별로 격리 된 로밍 저장소를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-157">The following code example retrieves a roaming store isolated by user and assembly.</span></span> <span data-ttu-id="9ad82-158">스토어를 통해 액세스할 수는 `isoFile` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-158">The store can be accessed through the `isoFile` object.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 <span data-ttu-id="9ad82-159">도메인 범위는 로밍 사용자, 도메인 및 응용 프로그램 별로 격리 된 저장소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-159">A domain scope can be added to create a roaming store isolated by user, domain, and application.</span></span> <span data-ttu-id="9ad82-160">다음 코드 예제에서는이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ad82-160">The following code example demonstrates this.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="9ad82-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ad82-161">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [<span data-ttu-id="9ad82-162">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="9ad82-162">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
