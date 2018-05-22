---
title: '방법: 격리된 저장소의 저장소 가져오기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 604aabbff8554416d6794ff0b87188fb5bcc3185
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a><span data-ttu-id="c3fb8-102">방법: 격리된 저장소의 저장소 가져오기</span><span class="sxs-lookup"><span data-stu-id="c3fb8-102">How to: Obtain Stores for Isolated Storage</span></span>
<span data-ttu-id="c3fb8-103">격리된 저장소는 데이터 구획 내에서 가상 파일 시스템을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-103">An isolated store exposes a virtual file system within a data compartment.</span></span> <span data-ttu-id="c3fb8-104"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> 클래스는 격리된 저장소와 상호 작용하는 데 필요한 여러 가지 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-104">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class supplies a number of methods for interacting with an isolated store.</span></span> <span data-ttu-id="c3fb8-105">저장소를 만들고 검색하기 위해 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>은 세 가지 정적 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-105">To create and retrieve stores, <xref:System.IO.IsolatedStorage.IsolatedStorageFile> provides three static methods:</span></span>  
  
-   <span data-ttu-id="c3fb8-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>는 사용자와 어셈블리별로 격리된 저장소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> returns storage that is isolated by user and assembly.</span></span>  
  
-   <span data-ttu-id="c3fb8-107"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>은 도메인과 어셈블리별로 격리된 저장소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-107"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> returns storage that is isolated by domain and assembly.</span></span>  
  
     <span data-ttu-id="c3fb8-108">이 두 메서드는 모두 자신이 호출되는 코드에 속하는 저장소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-108">Both methods retrieve a store that belongs to the code from which they are called.</span></span>  
  
-   <span data-ttu-id="c3fb8-109">정적 메서드 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>는 범위 매개 변수의 조합을 전달하여 지정된 격리된 저장소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-109">The static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> returns an isolated store that is specified by passing in a combination of scope parameters.</span></span>  
  
 <span data-ttu-id="c3fb8-110">다음 코드는 사용자, 어셈블리 및 도메인별로 격리된 저장소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-110">The following code returns a store that is isolated by user, assembly, and domain.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 <span data-ttu-id="c3fb8-111"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드를 사용하여 로밍 사용자 프로필과 함께 저장소를 로밍하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-111">You can use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method to specify that a store should roam with a roaming user profile.</span></span> <span data-ttu-id="c3fb8-112">이를 설정하는 방법에 대한 자세한 내용은 [격리 유형](../../../docs/standard/io/types-of-isolation.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-112">For details on how to set this up, see [Types of Isolation](../../../docs/standard/io/types-of-isolation.md).</span></span>  
  
 <span data-ttu-id="c3fb8-113">다른 어셈블리 내에서 얻은 격리된 저장소는 기본적으로 서로 다른 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-113">Isolated stores obtained from within different assemblies are, by default, different stores.</span></span> <span data-ttu-id="c3fb8-114">어셈블리 또는 도메인 증명을 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드의 매개 변수에서 전달하여 다른 어셈블리 또는 도메인의 저장소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-114">You can access the store of a different assembly or domain by passing in the assembly or domain evidence in the parameters of the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="c3fb8-115">그렇게 하려면 응용 프로그램 도메인 ID별로 격리된 저장소에 액세스할 수 있는 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-115">This requires permission to access isolated storage by application domain identity.</span></span> <span data-ttu-id="c3fb8-116">자세한 내용은 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드 오버로드를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-116">For more information, see the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method overloads.</span></span>  
  
 <span data-ttu-id="c3fb8-117"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> 및 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-117">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> methods return an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> object.</span></span> <span data-ttu-id="c3fb8-118">상황에 가장 적합한 격리 유형을 결정하는 데 도움을 받으려면 [격리 유형](../../../docs/standard/io/types-of-isolation.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-118">To help you decide which isolation type is most appropriate for your situation, see [Types of Isolation](../../../docs/standard/io/types-of-isolation.md).</span></span> <span data-ttu-id="c3fb8-119">격리된 저장소 파일 개체가 있으면 격리된 저장소 메서드를 사용하여 파일과 디렉터리를 읽고 쓰고 만들고 삭제하는 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-119">When you have an isolated storage file object, you can use the isolated storage methods to read, write, create, and delete files and directories.</span></span>  
  
 <span data-ttu-id="c3fb8-120">코드가 저장소 자체를 가져올 수 있는 액세스 권한이 충분하지 않은 코드에 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체를 전달하지 못하도록 하는 메커니즘은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-120">There is no mechanism that prevents code from passing an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> object to code that does not have sufficient access to get the store itself.</span></span> <span data-ttu-id="c3fb8-121">도메인 및 어셈블리 ID 및 격리된 저장소 권한은 <xref:System.IO.IsolatedStorage.IsolatedStorage> 개체에 대한 참조를 일반적으로 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> 또는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 메서드에서 가져온 경우에만 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-121">Domain and assembly identities and isolated storage permissions are checked only when a reference to an <xref:System.IO.IsolatedStorage.IsolatedStorage> object is obtained, typically in the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, or <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="c3fb8-122">따라서 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체에 대한 참조를 보호하는 것은 이러한 참조를 사용하는 코드의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-122">Protecting references to <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects is, therefore, the responsibility of the code that uses these references.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3fb8-123">예</span><span class="sxs-lookup"><span data-stu-id="c3fb8-123">Example</span></span>  
 <span data-ttu-id="c3fb8-124">다음 코드에서는 사용자 및 어셈블리별로 격리된 저장소를 가져오는 클래스의 간단한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-124">The following code provides a simple example of a class obtaining a store that is isolated by user and assembly.</span></span> <span data-ttu-id="c3fb8-125"><xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> 메서드가 전달하는 인수에 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>을 추가하면 사용자, 도메인 및 어셈블리별로 격리된 저장소를 검색하도록 코드를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-125">The code can be changed to retrieve a store that is isolated by user, domain, and assembly by adding <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> to the arguments that the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method passes.</span></span>  
  
 <span data-ttu-id="c3fb8-126">코드를 실행한 후 명령줄에 **StoreAdm /LIST**를 입력하여 저장소가 생성되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-126">After you run the code, you can confirm that a store was created by typing **StoreAdm /LIST** at the command line.</span></span> <span data-ttu-id="c3fb8-127">이렇게 하면 [격리된 저장소 도구(Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md)가 실행되어 사용자에 대해 현재 격리된 저장소가 모두 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3fb8-127">This runs the [Isolated Storage tool (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) and lists all the current isolated stores for the user.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="c3fb8-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3fb8-128">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [<span data-ttu-id="c3fb8-129">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="c3fb8-129">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="c3fb8-130">격리 유형</span><span class="sxs-lookup"><span data-stu-id="c3fb8-130">Types of Isolation</span></span>](../../../docs/standard/io/types-of-isolation.md)  
 [<span data-ttu-id="c3fb8-131">공용 언어 런타임의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c3fb8-131">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
