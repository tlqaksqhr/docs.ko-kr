---
title: 격리 유형
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0c888181b5f2150c37a87957cd932e10a36f7f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="types-of-isolation"></a><span data-ttu-id="082d5-102">격리 유형</span><span class="sxs-lookup"><span data-stu-id="082d5-102">Types of Isolation</span></span>
<span data-ttu-id="082d5-103">격리된 저장소에 대한 액세스는 항상 저장소를 만든 사용자로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-103">Access to isolated storage is always restricted to the user who created it.</span></span> <span data-ttu-id="082d5-104">이 유형의 격리를 구현하기 위해 공용 언어 런타임은 운영 체제에서 인식하고 저장소가 열릴 때 코드가 실행 중인 프로세스에 연결된 ID인 사용자 ID의 동일한 표기법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-104">To implement this type of isolation, the common language runtime uses the same notion of user identity that the operating system recognizes, which is the identity associated with the process in which the code is running when the store is opened.</span></span> <span data-ttu-id="082d5-105">이 ID는 인증된 사용자 ID이지만 가장으로 인해 현재 사용자의 ID가 동적으로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-105">This identity is an authenticated user identity, but impersonation can cause the identity of the current user to change dynamically.</span></span>  
  
 <span data-ttu-id="082d5-106">격리된 저장소에 대한 액세스는 응용 프로그램의 도메인 및 어셈블리에 연결되거나 어셈블리에만 연결된 ID에 따라 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-106">Access to isolated storage is also restricted according to the identity associated with the application's domain and assembly, or with the assembly alone.</span></span> <span data-ttu-id="082d5-107">런타임은 다음과 같은 방법으로 이러한 ID를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-107">The runtime obtains these identities in the following ways:</span></span>  
  
-   <span data-ttu-id="082d5-108">도메인 ID는 응용 프로그램의 증거를 나타내며 웹 응용 프로그램의 경우 전체 URL일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-108">Domain identity represents the evidence of the application, which in the case of a web application might be the full URL.</span></span> <span data-ttu-id="082d5-109">셸에 호스트된 코드의 경우 도메인 ID는 응용 프로그램 디렉터리 경로를 기반으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-109">For shell-hosted code, the domain identity might be based on the application directory path.</span></span> <span data-ttu-id="082d5-110">예를 들어 실행 파일이 C:\Office\MyApp.exe 경로에서 실행되는 경우 도메인 ID는 C:\Office\MyApp.exe입니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-110">For example, if the executable runs from the path C:\Office\MyApp.exe, the domain identity would be C:\Office\MyApp.exe.</span></span>  
  
-   <span data-ttu-id="082d5-111">어셈블리 ID는 어셈블리의 증거입니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-111">Assembly identity is the evidence of the assembly.</span></span> <span data-ttu-id="082d5-112">이 ID는 암호화 디지털 서명에서 가져올 수 있고 어셈블리의 [강력한 이름](../../../docs/framework/app-domains/strong-named-assemblies.md), 어셈블리의 소프트웨어 게시자 또는 해당 URL ID가 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-112">This might come from a cryptographic digital signature, which can be the assembly's [strong name](../../../docs/framework/app-domains/strong-named-assemblies.md), the software publisher of the assembly, or its URL identity.</span></span> <span data-ttu-id="082d5-113">어셈블리에 강력한 이름과 소프트웨어 게시자 ID가 모두 있는 경우 소프트웨어 게시자 ID가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-113">If an assembly has both a strong name and a software publisher identity, then the software publisher identity is used.</span></span> <span data-ttu-id="082d5-114">어셈블리를 인터넷에서 가져오고 서명이 없는 경우 URL ID가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-114">If the assembly comes from the Internet and is unsigned, the URL identity is used.</span></span> <span data-ttu-id="082d5-115">어셈블리 및 강력한 이름에 대한 자세한 내용은 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="082d5-115">For more information about assemblies and strong names, see [Programming with Assemblies](../../../docs/framework/app-domains/programming-with-assemblies.md).</span></span>  
  
-   <span data-ttu-id="082d5-116">로밍 저장소는 로밍 사용자 프로필이 있는 사용자와 함께 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-116">Roaming stores move with a user that has a roaming user profile.</span></span> <span data-ttu-id="082d5-117">파일은 네트워크 디렉터리에 기록되고 사용자가 로그인한 컴퓨터로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-117">Files are written to a network directory and are downloaded to any computer the user logs into.</span></span> <span data-ttu-id="082d5-118">로밍 사용자 프로필에 대한 자세한 내용은 <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="082d5-118">For more information about roaming user profiles, see <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="082d5-119">사용자, 도메인 및 어셈블리 ID의 개념을 결합하면 격리된 저장소가 다음 방법으로 데이터를 격리할 수 있으며 각 방법에는 고유한 사용 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-119">By combining the concepts of user, domain, and assembly identity, isolated storage can isolate data in the following ways, each of which has its own usage scenarios:</span></span>  
  
-   [<span data-ttu-id="082d5-120">사용자 및 어셈블리별 격리</span><span class="sxs-lookup"><span data-stu-id="082d5-120">Isolation by user and assembly</span></span>](#UserAssembly)  
  
-   [<span data-ttu-id="082d5-121">사용자, 도메인 및 어셈블리별 격리</span><span class="sxs-lookup"><span data-stu-id="082d5-121">Isolation by user, domain, and assembly</span></span>](#UserDomainAssembly)  
  
 <span data-ttu-id="082d5-122">이러한 경리 중 하나가 로밍 사용자 프로필과 결합될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-122">Either of these isolations can be combined with a roaming user profile.</span></span> <span data-ttu-id="082d5-123">자세한 내용은 [격리된 저장소 및 로밍](#Roaming) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="082d5-123">For more information, see the section [Isolated Storage and Roaming](#Roaming).</span></span>  
  
 <span data-ttu-id="082d5-124">다음 그림은 저장소를 여러 범위로 격리하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-124">The following illustration demonstrates how stores are isolated in different scopes.</span></span>  
  
 <span data-ttu-id="082d5-125">![사용자 및 어셈블리별 격리](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")</span><span class="sxs-lookup"><span data-stu-id="082d5-125">![Isolation by user and assembly](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")</span></span>  
<span data-ttu-id="082d5-126">격리된 저장소 유형</span><span class="sxs-lookup"><span data-stu-id="082d5-126">Types of isolated storage</span></span>  
  
 <span data-ttu-id="082d5-127">로밍 저장소를 제외하고 격리된 저장소는 지정된 컴퓨터에 로컬인 저장소 시설을 사용하므로 항상 컴퓨터에서 암시적으로 격리됩니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-127">Note that except for roaming stores, isolated storage is always implicitly isolated by computer because it uses the storage facilities that are local to a given computer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="082d5-128">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 응용 프로그램에는 격리된 저장소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-128">Isolated storage is not available for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="082d5-129">대신에 `Windows.Storage` API에 포함된 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 네임스페이스의 응용 프로그램 데이터 클래스를 사용하여 로컬 데이터 및 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-129">Instead, use the application data classes in the `Windows.Storage` namespaces included in the [!INCLUDE[wrt](../../../includes/wrt-md.md)] API to store local data and files.</span></span> <span data-ttu-id="082d5-130">자세한 내용은 Windows 개발자 센터에서 [응용 프로그램 데이터](/previous-versions/windows/apps/hh464917(v=win.10))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="082d5-130">For more information, see [Application data](/previous-versions/windows/apps/hh464917(v=win.10)) in the Windows Dev Center.</span></span>  
  
<a name="UserAssembly"></a>   
## <a name="isolation-by-user-and-assembly"></a><span data-ttu-id="082d5-131">사용자 및 어셈블리별 격리</span><span class="sxs-lookup"><span data-stu-id="082d5-131">Isolation by User and Assembly</span></span>  
 <span data-ttu-id="082d5-132">데이터 저장소를 사용하는 어셈블리를 응용 프로그램 도메인에서 액세스할 수 있어야 하는 경우 사용자 및 어셈블리별로 격리하는 것이 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-132">When the assembly that uses the data store needs to be accessible from any application's domain, isolation by user and assembly is appropriate.</span></span> <span data-ttu-id="082d5-133">일반적으로 이 상황에서 격리된 저장소는 여러 응용 프로그램에 적용되는 데이터를 저장하는 데 사용되며 사용자 이름 또는 라이선스 정보와 같은 특정 응용 프로그램에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-133">Typically, in this situation, isolated storage is used to store data that applies across multiple applications and is not tied to any particular application, such as the user's name or license information.</span></span> <span data-ttu-id="082d5-134">사용자 및 어셈블리별로 격리된 저장소에 액세스하려면 응용 프로그램 간에 정보를 전송하기 위해 코드를 신뢰할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-134">To access storage isolated by user and assembly, code must be trusted to transfer information between applications.</span></span> <span data-ttu-id="082d5-135">일반적으로 사용자 및 어셈블리별 격리는 인트라넷에서 허용되지만 인터넷에는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-135">Typically, isolation by user and assembly is allowed on intranets but not on the Internet.</span></span> <span data-ttu-id="082d5-136">정적 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType> 메서드를 호출하고 사용자 및 어셈블리로 전달하면 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>는 이 유형의 격리를 통해 저장소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-136">Calling the static <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType> method and passing in a user and an assembly <xref:System.IO.IsolatedStorage.IsolatedStorageScope> returns storage with this kind of isolation.</span></span>  
  
 <span data-ttu-id="082d5-137">다음 코드 예제에서는 사용자 및 어셈블리별로 격리되는 저장소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-137">The following code example retrieves a store that is isolated by user and assembly.</span></span> <span data-ttu-id="082d5-138">`isoFile` 개체를 통해 저장소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-138">The store can be accessed through the `isoFile` object.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 <span data-ttu-id="082d5-139">증거 매개 변수를 사용하는 예제는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="082d5-139">For an example that uses the evidence parameters, see <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.</span></span>  
  
 <span data-ttu-id="082d5-140"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> 메서드는 다음 코드 예제와 같이 바로 가기로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-140">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> method is available as a shortcut, as shown in the following code example.</span></span> <span data-ttu-id="082d5-141">이 바로 가기는 로밍할 수 있는 저장소를 여는 데 사용할 수 없습니다. 이 경우에는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-141">This shortcut cannot be used to open stores that are capable of roaming; use <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> in such cases.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>   
## <a name="isolation-by-user-domain-and-assembly"></a><span data-ttu-id="082d5-142">사용자, 도메인 및 어셈블리별 격리</span><span class="sxs-lookup"><span data-stu-id="082d5-142">Isolation by User, Domain, and Assembly</span></span>  
 <span data-ttu-id="082d5-143">응용 프로그램에서 개인 데이터 저장소가 필요한 타사 어셈블리를 사용하는 경우 격리된 저장소를 사용하여 개인 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-143">If your application uses a third-party assembly that requires a private data store, you can use isolated storage to store the private data.</span></span> <span data-ttu-id="082d5-144">사용자, 도메인 및 어셈블리별 격리를 사용하면 어셈블리가 저장소를 만들 때 실행 중이던 응용 프로그램에서 어셈블리가 사용될 경우 및 저장소를 만든 사용자가 응용 프로그램을 실행하는 경우에만 지정된 어셈블리의 코드만 해당 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-144">Isolation by user, domain, and assembly ensures that only code in a given assembly can access the data, and only when the assembly is used by the application that was running when the assembly created the store, and only when the user for whom the store was created runs the application.</span></span> <span data-ttu-id="082d5-145">사용자, 도메인 및 어셈블리별 격리를 사용하면 타사 어셈블리에 의해 데이터가 다른 응용 프로그램으로 누출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-145">Isolation by user, domain, and assembly keeps the third-party assembly from leaking data to other applications.</span></span> <span data-ttu-id="082d5-146">격리된 저장소를 사용하려고 하지만 어떤 격리 유형을 사용할지 확신할 수 없는 경우에는 기본적으로 이 격리 유형을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-146">This isolation type should be your default choice if you know that you want to use isolated storage but are not sure which type of isolation to use.</span></span> <span data-ttu-id="082d5-147"><xref:System.IO.IsolatedStorage.IsolatedStorageFile>의 정적 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드를 호출하고 사용자, 도메인 및 어셈블리로 전달하면 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>는 이 유형의 격리를 통해 저장소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-147">Calling the static <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method of <xref:System.IO.IsolatedStorage.IsolatedStorageFile> and passing in a user, domain, and assembly <xref:System.IO.IsolatedStorage.IsolatedStorageScope> returns storage with this kind of isolation.</span></span>  
  
 <span data-ttu-id="082d5-148">다음 코드 예제에서는 사용자, 도메인 및 어셈블리별로 격리되는 저장소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-148">The following code example retrieves a store isolated by user, domain, and assembly.</span></span> <span data-ttu-id="082d5-149">`isoFile` 개체를 통해 저장소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-149">The store can be accessed through the `isoFile` object.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 <span data-ttu-id="082d5-150">또 다른 메서드는 다음 코드 예제와 같이 바로 가기로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-150">Another method is available as a shortcut, as shown in the following code example.</span></span> <span data-ttu-id="082d5-151">이 바로 가기는 로밍할 수 있는 저장소를 여는 데 사용할 수 없습니다. 이 경우에는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-151">This shortcut cannot be used to open stores that are capable of roaming; use <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> in such cases.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>   
## <a name="isolated-storage-and-roaming"></a><span data-ttu-id="082d5-152">격리된 저장소 및 로밍</span><span class="sxs-lookup"><span data-stu-id="082d5-152">Isolated Storage and Roaming</span></span>  
 <span data-ttu-id="082d5-153">로밍 사용자 프로필은 사용자가 네트워크에서 ID를 설정하고 해당 ID를 사용하여 모든 개인 설정을 적용하여 네트워크 컴퓨터에 로그인하도록 하는 Windows 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-153">Roaming user profiles are a Windows feature that enables a user to set up an identity on a network and use that identity to log into any network computer, carrying over all personalized settings.</span></span> <span data-ttu-id="082d5-154">격리된 저장소를 사용하는 어셈블리는 사용자의 격리된 저장소가 로밍 사용자 프로필과 함께 이동되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-154">An assembly that uses isolated storage can specify that the user's isolated storage should move with the roaming user profile.</span></span> <span data-ttu-id="082d5-155">로밍은 사용자 및 어셈블리별 격리 및 사용자, 도메인 및 어셈블리별 격리와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-155">Roaming can be used in conjunction with isolation by user and assembly or with isolation by user, domain, and assembly.</span></span> <span data-ttu-id="082d5-156">로밍 범위를 사용하지 않으면 로밍 사용자 프로필이 사용되는 경우에도 저장소가 로밍되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-156">If a roaming scope is not used, stores will not roam even if a roaming user profile is used.</span></span>  
  
 <span data-ttu-id="082d5-157">다음 코드 예제에서는 사용자 및 어셈블리별로 격리된 로밍 저장소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-157">The following code example retrieves a roaming store isolated by user and assembly.</span></span> <span data-ttu-id="082d5-158">`isoFile` 개체를 통해 저장소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-158">The store can be accessed through the `isoFile` object.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 <span data-ttu-id="082d5-159">사용자, 도메인 및 응용 프로그램별로 격리된 로밍 저장소를 만들 위해 도메인 범위를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-159">A domain scope can be added to create a roaming store isolated by user, domain, and application.</span></span> <span data-ttu-id="082d5-160">다음 코드 예제에서는 이 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="082d5-160">The following code example demonstrates this.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="082d5-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="082d5-161">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [<span data-ttu-id="082d5-162">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="082d5-162">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
