---
title: "메모리 매핑된 파일"
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
helpviewer_keywords:
- memory-mapped files
- inter-process communiation
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 99aefdaf3d38dc5506bf785c8ba4a9b457cc7bf7
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="memory-mapped-files"></a><span data-ttu-id="549f6-102">메모리 매핑된 파일</span><span class="sxs-lookup"><span data-stu-id="549f6-102">Memory-Mapped Files</span></span>
<span data-ttu-id="549f6-103">메모리 매핑된 파일에는 가상 메모리에 있는 파일의 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-103">A memory-mapped file contains the contents of a file in virtual memory.</span></span> <span data-ttu-id="549f6-104">파일과 메모리 공간 사이의 매핑을 사용하면 여러 프로세스를 포함한 응용 프로그램이 메모리에 직접 읽고 쓰는 방식으로 파일을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-104">This mapping between a file and memory space enables an application, including multiple processes, to modify the file by reading and writing directly to the memory.</span></span> <span data-ttu-id="549f6-105">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 네이티브 Windows 함수가 메모리 매핑된 파일에 액세스할 때와 같은 방식으로 관리 코드를 사용하여 메모리 매핑된 파일에 액세스할 수 있습니다. 이에 대해서는 [메모리 매핑된 파일 관리](https://msdn.microsoft.com/library/ms810613.aspx)에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-105">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use managed code to access memory-mapped files in the same way that native Windows functions access memory-mapped files, as described in [Managing Memory-Mapped Files](https://msdn.microsoft.com/library/ms810613.aspx).</span></span>  
  
 <span data-ttu-id="549f6-106">메모리 매핑된 파일에는 다음과 같은 두 가지 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-106">There are two types of memory-mapped files:</span></span>  
  
-   <span data-ttu-id="549f6-107">지속되는 메모리 매핑된 파일</span><span class="sxs-lookup"><span data-stu-id="549f6-107">Persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="549f6-108">지속되는 파일은 디스크에서 소스 파일과 연결된 메모리 매핑된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-108">Persisted files are memory-mapped files that are associated with a source file on a disk.</span></span> <span data-ttu-id="549f6-109">마지막 프로세스가 파일에 대한 작업을 완료하면 데이터가 디스크의 소스 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-109">When the last process has finished working with the file, the data is saved to the source file on the disk.</span></span> <span data-ttu-id="549f6-110">이러한 메모리 매핑된 파일은 매우 큰 소스 파일에 대한 작업에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-110">These memory-mapped files are suitable for working with extremely large source files.</span></span>  
  
-   <span data-ttu-id="549f6-111">지속되지 않는 메모리 매핑된 파일</span><span class="sxs-lookup"><span data-stu-id="549f6-111">Non-persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="549f6-112">지속되지 않는 파일은 디스크에서 파일과 연결되지 않은 메모리 매핑된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-112">Non-persisted files are memory-mapped files that are not associated with a file on a disk.</span></span> <span data-ttu-id="549f6-113">마지막 프로세스가 파일에 대한 작업을 완료하면 데이터가 손실되고 파일이 가비지 수집에 의해 회수됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-113">When the last process has finished working with the file, the data is lost and the file is reclaimed by garbage collection.</span></span> <span data-ttu-id="549f6-114">이러한 파일은 IPC(프로세스 간 통신)에 대한 공유 메모리를 만드는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-114">These files are suitable for creating shared memory for inter-process communications (IPC).</span></span>  
  
## <a name="processes-views-and-managing-memory"></a><span data-ttu-id="549f6-115">프로세스, 보기 및 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="549f6-115">Processes, Views, and Managing Memory</span></span>  
 <span data-ttu-id="549f6-116">메모리 매핑된 파일은 여러 프로세스에서 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-116">Memory-mapped files can be shared across multiple processes.</span></span> <span data-ttu-id="549f6-117">파일을 만든 프로세스에서 할당한 일반 이름을 사용하여 동일한 메모리 매핑된 파일에 프로세스를 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-117">Processes can map to the same memory-mapped file by using a common name that is assigned by the process that created the file.</span></span>  
  
 <span data-ttu-id="549f6-118">메모리 매핑된 파일을 사용하려면 전체 메모리 매핑된 파일 또는 파일의 일부분에 대한 보기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-118">To work with a memory-mapped file, you must create a view of the entire memory-mapped file or a part of it.</span></span> <span data-ttu-id="549f6-119">메모리 매핑된 파일의 동일한 부분에 대한 여러 보기를 만들어서 동시 메모리를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-119">You can also create multiple views to the same part of the memory-mapped file, thereby creating concurrent memory.</span></span> <span data-ttu-id="549f6-120">두 보기를 동시에 유지하려면 동일한 메모리 매핑된 파일에서 보기를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-120">For two views to remain concurrent, they have to be created from the same memory-mapped file.</span></span>  
  
 <span data-ttu-id="549f6-121">파일이 메모리 매핑에 사용 가능한 응용 프로그램의 논리 메모리 공간 크기(32비트 컴퓨터의 2GB)보다 크면 여러 보기가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-121">Multiple views may also be necessary if the file is greater than the size of the application’s logical memory space available for memory mapping (2 GB on a 32-bit computer).</span></span>  
  
 <span data-ttu-id="549f6-122">스트림 액세스 보기 및 임의 액세스 보기라는 두 가지 유형의 보기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-122">There are two types of views: stream access view and random access view.</span></span> <span data-ttu-id="549f6-123">파일에 대한 순차적 액세스에는 스트림 액세스 보기를 사용합니다. 이 보기는 지속되지 않는 파일 및 IPC에는 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-123">Use stream access views for sequential access to a file; this is recommended for non-persisted files and IPC.</span></span> <span data-ttu-id="549f6-124">임의 액세스 보기는 지속되는 파일 작업에 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-124">Random access views are preferred for working with persisted files.</span></span>  
  
 <span data-ttu-id="549f6-125">메모리 매핑된 파일은 운영 체제의 메모리 관리자를 통해 액세스되므로 파일은 여러 페이지에 자동으로 분할되고 필요에 따라 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-125">Memory-mapped files are accessed through the operating system’s memory manager, so the file is automatically partitioned into a number of pages and accessed as needed.</span></span> <span data-ttu-id="549f6-126">메모리 관리를 직접 처리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-126">You do not have to handle the memory management yourself.</span></span>  
  
 <span data-ttu-id="549f6-127">다음 그림은 여러 프로세스에서 동시에 동일한 메모리 매핑된 파일에 대한 여러 개의 중첩된 보기를 생성하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-127">The following illustration shows how multiple processes can have multiple and overlapping views to the same memory-mapped file at the same time.</span></span>  
  
 <span data-ttu-id="549f6-128">![메모리 매핑된 파일에 대한 보기를 보여줍니다.](../../../docs/standard/io/media/memmappersisted.png " MemMapPersisted")</span><span class="sxs-lookup"><span data-stu-id="549f6-128">![Shows views to a memory&#45;mapped file.](../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")</span></span>  
<span data-ttu-id="549f6-129">메모리 매핑된 파일에 대한 여러 개의 중첩된 보기</span><span class="sxs-lookup"><span data-stu-id="549f6-129">Multiple and overlapped views to a memory-mapped file</span></span>  
  
## <a name="programming-with-memory-mapped-files"></a><span data-ttu-id="549f6-130">메모리 매핑된 파일을 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="549f6-130">Programming with Memory-Mapped Files</span></span>  
 <span data-ttu-id="549f6-131">다음 표에서는 메모리 매핑된 파일 개체 및 해당 멤버 사용에 대한 가이드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-131">The following table provides a guide for using memory-mapped file objects and their members.</span></span>  
  
|<span data-ttu-id="549f6-132">작업</span><span class="sxs-lookup"><span data-stu-id="549f6-132">Task</span></span>|<span data-ttu-id="549f6-133">사용할 메서드 또는 속성</span><span class="sxs-lookup"><span data-stu-id="549f6-133">Methods or properties to use</span></span>|  
|----------|----------------------------------|  
|<span data-ttu-id="549f6-134">디스크의 파일에서 지속되는 메모리 매핑된 파일을 나타내는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-134">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a persisted memory-mapped file from a file on disk.</span></span>|<span data-ttu-id="549f6-135"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-135"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="549f6-136">지속되지 않는 메모리 매핑된 파일(디스크의 파일과 연결되지 않음)을 나타내는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-136">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a non-persisted memory-mapped file (not associated with a file on disk).</span></span>|<span data-ttu-id="549f6-137"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-137"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> method.</span></span><br /><br /> <span data-ttu-id="549f6-138">또는</span><span class="sxs-lookup"><span data-stu-id="549f6-138">- or -</span></span><br /><br /> <span data-ttu-id="549f6-139"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-139"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="549f6-140">기존 메모리 매핑된 파일(지속되는 파일 또는 지속되지 않는 파일)의 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-140">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object of an existing memory-mapped file (either persisted or non-persisted).</span></span>|<span data-ttu-id="549f6-141"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-141"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="549f6-142">메모리 매핑된 파일에 대한 순차적 액세스 보기의 <xref:System.IO.UnmanagedMemoryStream> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-142">To obtain a <xref:System.IO.UnmanagedMemoryStream> object for a sequentially accessed view to the memory-mapped file.</span></span>|<span data-ttu-id="549f6-143"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-143"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="549f6-144">메모리 매핑된 파일에 대한 임의 액세스 보기의 <xref:System.IO.UnmanagedMemoryAccessor> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-144">To obtain a <xref:System.IO.UnmanagedMemoryAccessor> object for a random access view to a memory-mapped fie.</span></span>|<span data-ttu-id="549f6-145"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-145"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="549f6-146">비관리 코드와 함께 사용할 <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-146">To obtain a <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> object to use with unmanaged code.</span></span>|<span data-ttu-id="549f6-147"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> 속성.</span><span class="sxs-lookup"><span data-stu-id="549f6-147"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="549f6-148">또는</span><span class="sxs-lookup"><span data-stu-id="549f6-148">- or -</span></span><br /><br /> <span data-ttu-id="549f6-149"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> 속성.</span><span class="sxs-lookup"><span data-stu-id="549f6-149"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="549f6-150">또는</span><span class="sxs-lookup"><span data-stu-id="549f6-150">- or -</span></span><br /><br /> <span data-ttu-id="549f6-151"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> 속성.</span><span class="sxs-lookup"><span data-stu-id="549f6-151"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="549f6-152">보기가 만들어질 때까지 메모리 할당을 지연시킵니다(지속되지 않는 파일만).</span><span class="sxs-lookup"><span data-stu-id="549f6-152">To delay allocating memory until a view is created (non-persisted files only).</span></span><br /><br /> <span data-ttu-id="549f6-153">(현재 시스템 페이지 크기를 확인하려면 <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> 속성을 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="549f6-153">(To determine the current system page size, use the <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> property.)</span></span>|<span data-ttu-id="549f6-154"><xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> 값을 가지는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="549f6-154"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> method with the <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> value.</span></span><br /><br /> <span data-ttu-id="549f6-155">또는</span><span class="sxs-lookup"><span data-stu-id="549f6-155">- or -</span></span><br /><br /> <span data-ttu-id="549f6-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> 열거형을 매개 변수로 사용하는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="549f6-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods that have a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> enumeration as a parameter.</span></span>|  
  
### <a name="security"></a><span data-ttu-id="549f6-157">보안</span><span class="sxs-lookup"><span data-stu-id="549f6-157">Security</span></span>  
 <span data-ttu-id="549f6-158"><xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> 열거형을 매개 변수로 사용하는 다음 메서드를 사용하여 메모리 매핑된 파일을 만들 때 액세스 권한을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-158">You can apply access rights when you create a memory-mapped file, by using the following methods that take a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> enumeration as a parameter:</span></span>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="549f6-159"><xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights>를 매개 변수로 사용하는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> 메서드를 사용하여 기존 메모리 매핑된 파일을 열기 위한 액세스 권한을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-159">You can specify access rights for opening an existing memory-mapped file by using the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> methods that take an <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> as a parameter.</span></span>  
  
 <span data-ttu-id="549f6-160">또한 미리 정의된 액세스 규칙을 포함하는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> 개체를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-160">In addition, you can include a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> object that contains predefined access rules.</span></span>  
  
 <span data-ttu-id="549f6-161">메모리 매핑된 파일에 새롭거나 변경된 액세스 규칙을 적용하려면 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-161">To apply new or changed access rules to a memory-mapped file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> method.</span></span> <span data-ttu-id="549f6-162">기존 파일에서 액세스 또는 감사 규칙을 검색하려면 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-162">To retrieve access or audit rules from an existing file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="549f6-163">예제</span><span class="sxs-lookup"><span data-stu-id="549f6-163">Examples</span></span>  
  
### <a name="persisted-memory-mapped-files"></a><span data-ttu-id="549f6-164">지속되는 메모리 매핑된 파일</span><span class="sxs-lookup"><span data-stu-id="549f6-164">Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="549f6-165"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> 메서드는 디스크의 기존 파일에서 메모리 매핑된 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-165">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> methods create a memory-mapped file from an existing file on disk.</span></span>  
  
 <span data-ttu-id="549f6-166">다음 예제에서는 매우 큰 파일의 일부에 대한 메모리 매핑된 보기를 만들고 보기의 일부를 조작합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-166">The following example creates a memory-mapped view of a part of an extremely large file and manipulates a portion of it.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 <span data-ttu-id="549f6-167">다음 예제에서는 다른 프로세스에 대한 동일한 메모리 매핑된 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-167">The following example opens the same memory-mapped file for another process.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a><span data-ttu-id="549f6-168">지속되지 않는 메모리 매핑된 파일</span><span class="sxs-lookup"><span data-stu-id="549f6-168">Non-Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="549f6-169"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> 및 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> 메서드는 디스크의 기존 파일에 매핑되지 않은 메모리 매핑된 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-169">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> and <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods create a memory-mapped file that is not mapped to an existing file on disk.</span></span>  
  
 <span data-ttu-id="549f6-170">다음 예제는 메모리 매핑된 파일에 부울 값을 쓰는 세 개의 개별 프로세스(콘솔 응용 프로그램)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-170">The following example consists of three separate processes (console applications) that write Boolean values to a memory-mapped file.</span></span> <span data-ttu-id="549f6-171">다음 작업 시퀀스가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-171">The following sequence of actions occur:</span></span>  
  
1.  <span data-ttu-id="549f6-172">`Process A`는 메모리 매핑된 파일을 만들고 이 파일에 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-172">`Process A` creates the memory-mapped file and writes a value to it.</span></span>  
  
2.  <span data-ttu-id="549f6-173">`Process B`는 메모리 매핑된 파일을 열고 이 파일에 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-173">`Process B` opens the memory-mapped file and writes a value to it.</span></span>  
  
3.  <span data-ttu-id="549f6-174">`Process C`는 메모리 매핑된 파일을 열고 이 파일에 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-174">`Process C` opens the memory-mapped file and writes a value to it.</span></span>  
  
4.  <span data-ttu-id="549f6-175">`Process A`는 메모리 매핑된 파일에서 값을 읽고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-175">`Process A` reads and displays the values from the memory-mapped file.</span></span>  
  
5.  <span data-ttu-id="549f6-176">`Process A`가 메모리 매핑된 파일로 완료된 후에는 가비지 수집에 의해 파일이 즉시 회수됩니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-176">After `Process A` is finished with the memory-mapped file, the file is immediately reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="549f6-177">이 예제를 실행하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-177">To run this example, do the following:</span></span>  
  
1.  <span data-ttu-id="549f6-178">응용 프로그램을 컴파일하고 세 개의 명령 프롬프트 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-178">Compile the applications and open three Command Prompt windows.</span></span>  
  
2.  <span data-ttu-id="549f6-179">첫 번째 명령 프롬프트 창에서 `Process A`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-179">In the first Command Prompt window, run `Process A`.</span></span>  
  
3.  <span data-ttu-id="549f6-180">두 번째 명령 프롬프트 창에서 `Process B`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-180">In the second Command Prompt window, run `Process B`.</span></span>  
  
4.  <span data-ttu-id="549f6-181">`Process A`로 돌아가서 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-181">Return to `Process A` and press ENTER.</span></span>  
  
5.  <span data-ttu-id="549f6-182">세 번째 명령 프롬프트 창에서 `Process C`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-182">In the third Command Prompt window, run `Process C`.</span></span>  
  
6.  <span data-ttu-id="549f6-183">`Process A`로 돌아가서 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-183">Return to `Process A` and press ENTER.</span></span>  
  
 <span data-ttu-id="549f6-184">`Process A`의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="549f6-184">The output of `Process A` is as follows:</span></span>  
  
```  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 <span data-ttu-id="549f6-185">**프로세스 A**</span><span class="sxs-lookup"><span data-stu-id="549f6-185">**Process A**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 <span data-ttu-id="549f6-186">**프로세스 B**</span><span class="sxs-lookup"><span data-stu-id="549f6-186">**Process B**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 <span data-ttu-id="549f6-187">**프로세스 C**</span><span class="sxs-lookup"><span data-stu-id="549f6-187">**Process C**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="549f6-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="549f6-188">See Also</span></span>  
 [<span data-ttu-id="549f6-189">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="549f6-189">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
