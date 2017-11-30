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
caps.latest.revision: "24"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2602d431aada7b3e0ee226eed319903492022ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="memory-mapped-files"></a><span data-ttu-id="cb024-102">메모리 매핑된 파일</span><span class="sxs-lookup"><span data-stu-id="cb024-102">Memory-Mapped Files</span></span>
<span data-ttu-id="cb024-103">메모리 매핑된 파일에는 가상 메모리에 있는 파일의 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-103">A memory-mapped file contains the contents of a file in virtual memory.</span></span> <span data-ttu-id="cb024-104">파일 및 메모리 공간 간의이 매핑을 통해 응용을 프로그램을 여러 프로세스를 포함 하는 메모리에 직접 읽고 파일을 수정 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-104">This mapping between a file and memory space enables an application, including multiple processes, to modify the file by reading and writing directly to the memory.</span></span> <span data-ttu-id="cb024-105">부터는 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], 관리 되는 코드를 사용 하 여에 설명 된 대로 메모리 매핑된 파일에는 네이티브 Windows 함수 메모리 매핑된 파일에 액세스 하는 것과 같은 방식으로 액세스할 수 [Win32에](http://go.microsoft.com/fwlink/?linkid=180801)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-105">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use managed code to access memory-mapped files in the same way that native Windows functions access memory-mapped files, as described in [Managing Memory-Mapped Files in Win32](http://go.microsoft.com/fwlink/?linkid=180801).</span></span>  
  
 <span data-ttu-id="cb024-106">메모리 매핑된 파일에는 다음과 같은 두 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-106">There are two types of memory-mapped files:</span></span>  
  
-   <span data-ttu-id="cb024-107">지속형된 메모리 매핑된 파일</span><span class="sxs-lookup"><span data-stu-id="cb024-107">Persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="cb024-108">지속형된 파일은 원본 디스크의 파일에는 연관 된 메모리 매핑된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-108">Persisted files are memory-mapped files that are associated with a source file on a disk.</span></span> <span data-ttu-id="cb024-109">마지막 프로세스 작업 파일을 마치고 나면, 데이터 디스크에 소스 파일에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-109">When the last process has finished working with the file, the data is saved to the source file on the disk.</span></span> <span data-ttu-id="cb024-110">이러한 메모리 매핑된 파일은 매우 큰 소스 파일 작업에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-110">These memory-mapped files are suitable for working with extremely large source files.</span></span>  
  
-   <span data-ttu-id="cb024-111">비지속형 메모리 매핑된 파일</span><span class="sxs-lookup"><span data-stu-id="cb024-111">Non-persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="cb024-112">비지속형 파일은 파일을 디스크에 연결 되지 않은 메모리 매핑된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-112">Non-persisted files are memory-mapped files that are not associated with a file on a disk.</span></span> <span data-ttu-id="cb024-113">마지막 프로세스 파일 작업을 마치고 나면, 데이터 손실 되 고 해당 파일이 가비지 수집에 의해 회수 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-113">When the last process has finished working with the file, the data is lost and the file is reclaimed by garbage collection.</span></span> <span data-ttu-id="cb024-114">이러한 파일은 프로세스 간 통신 (IPC)에 대 한 공유 메모리를 만들기에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-114">These files are suitable for creating shared memory for inter-process communications (IPC).</span></span>  
  
## <a name="processes-views-and-managing-memory"></a><span data-ttu-id="cb024-115">프로세스, 뷰 및 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="cb024-115">Processes, Views, and Managing Memory</span></span>  
 <span data-ttu-id="cb024-116">여러 프로세스에서 메모리 매핑된 파일을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-116">Memory-mapped files can be shared across multiple processes.</span></span> <span data-ttu-id="cb024-117">프로세스는 파일을 만든 프로세스에 의해 할당 된 일반 이름을 사용 하 여 동일한 메모리 매핑된 파일에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-117">Processes can map to the same memory-mapped file by using a common name that is assigned by the process that created the file.</span></span>  
  
 <span data-ttu-id="cb024-118">메모리 매핑된 파일을 사용 하려면의 일부 또는 전체 메모리 매핑된 파일의 뷰를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-118">To work with a memory-mapped file, you must create a view of the entire memory-mapped file or a part of it.</span></span> <span data-ttu-id="cb024-119">메모리 매핑된 파일의 한 부분을 위해 여러 뷰를 만들어 동시 메모리 제한을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-119">You can also create multiple views to the same part of the memory-mapped file, thereby creating concurrent memory.</span></span> <span data-ttu-id="cb024-120">동시을 유지 하기 위한 두 보기에 대 한 동일한 메모리 매핑된 파일에서 만들 수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-120">For two views to remain concurrent, they have to be created from the same memory-mapped file.</span></span>  
  
 <span data-ttu-id="cb024-121">여러 뷰 파일은 메모리 (32 비트 컴퓨터에서 2GB) 매핑에 사용할 수 있는 응용 프로그램의 논리 메모리 공간의 크기 보다 큰 경우에 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-121">Multiple views may also be necessary if the file is greater than the size of the application’s logical memory space available for memory mapping (2 GB on a 32-bit computer).</span></span>  
  
 <span data-ttu-id="cb024-122">두 가지 방법으로 뷰의: 스트림 액세스 뷰와 임의 액세스 보기.</span><span class="sxs-lookup"><span data-stu-id="cb024-122">There are two types of views: stream access view and random access view.</span></span> <span data-ttu-id="cb024-123">스트림 액세스 뷰를 사용 하 여 파일로; 순차적 액세스를 위해 이 방법은 비지속형 파일과 IPC에 대 한 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-123">Use stream access views for sequential access to a file; this is recommended for non-persisted files and IPC.</span></span> <span data-ttu-id="cb024-124">임의 액세스 뷰가 지속형된 파일 작업에 대 한 기본 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-124">Random access views are preferred for working with persisted files.</span></span>  
  
 <span data-ttu-id="cb024-125">파일은 자동으로 페이지 수로 분할 하 고 필요에 따라 액세스 되므로 메모리 매핑된 파일 운영 체제의 메모리 관리자를 통해 액세스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-125">Memory-mapped files are accessed through the operating system’s memory manager, so the file is automatically partitioned into a number of pages and accessed as needed.</span></span> <span data-ttu-id="cb024-126">메모리 관리를 직접 처리 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-126">You do not have to handle the memory management yourself.</span></span>  
  
 <span data-ttu-id="cb024-127">다음 그림과 방법을 여러 프로세스 점이 여러 하 고 동시에 동일한 메모리 매핑된 파일에 봅니다 겹치는 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-127">The following illustration shows how multiple processes can have multiple and overlapping views to the same memory-mapped file at the same time.</span></span>  
  
 <span data-ttu-id="cb024-128">![표시 뷰는 메모리 및 # 45를; 매핑된 파일입니다. ] (../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")</span><span class="sxs-lookup"><span data-stu-id="cb024-128">![Shows views to a memory&#45;mapped file.](../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")</span></span>  
<span data-ttu-id="cb024-129">여러 메모리 매핑된 파일에는 뷰를 서로 겹치는</span><span class="sxs-lookup"><span data-stu-id="cb024-129">Multiple and overlapped views to a memory-mapped file</span></span>  
  
## <a name="programming-with-memory-mapped-files"></a><span data-ttu-id="cb024-130">메모리 매핑된 파일을 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="cb024-130">Programming with Memory-Mapped Files</span></span>  
 <span data-ttu-id="cb024-131">다음 표에서 메모리 매핑된 파일 개체와 해당 멤버를 사용 하기 위한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-131">The following table provides a guide for using memory-mapped file objects and their members.</span></span>  
  
|<span data-ttu-id="cb024-132">작업</span><span class="sxs-lookup"><span data-stu-id="cb024-132">Task</span></span>|<span data-ttu-id="cb024-133">메서드 또는 속성을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="cb024-133">Methods or properties to use</span></span>|  
|----------|----------------------------------|  
|<span data-ttu-id="cb024-134">가져올 수는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 디스크에 파일에서 지속형된 메모리 매핑된 파일을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-134">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a persisted memory-mapped file from a file on disk.</span></span>|<span data-ttu-id="cb024-135"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-135"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="cb024-136">가져올 수는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 비지속형 메모리 매핑된 파일 (파일 디스크에 연결 되지 않음)을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-136">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a non-persisted memory-mapped file (not associated with a file on disk).</span></span>|<span data-ttu-id="cb024-137"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-137"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> method.</span></span><br /><br /> <span data-ttu-id="cb024-138">또는</span><span class="sxs-lookup"><span data-stu-id="cb024-138">- or -</span></span><br /><br /> <span data-ttu-id="cb024-139"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-139"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="cb024-140">가져올 수는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 기존 메모리 매핑된 파일의 (지속형 또는 비지속형) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-140">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object of an existing memory-mapped file (either persisted or non-persisted).</span></span>|<span data-ttu-id="cb024-141"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-141"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="cb024-142">가져올 수는 <xref:System.IO.UnmanagedMemoryStream> 메모리 매핑된 파일에 순차적으로 액세스 보기에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-142">To obtain a <xref:System.IO.UnmanagedMemoryStream> object for a sequentially accessed view to the memory-mapped file.</span></span>|<span data-ttu-id="cb024-143"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-143"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="cb024-144">가져올 수는 <xref:System.IO.UnmanagedMemoryAccessor> 개체에 대 한 임의 액세스 보기 메모리 매핑된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-144">To obtain a <xref:System.IO.UnmanagedMemoryAccessor> object for a random access view to a memory-mapped fie.</span></span>|<span data-ttu-id="cb024-145"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-145"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="cb024-146">가져올 수는 <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> 비관리 코드와 사용할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-146">To obtain a <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> object to use with unmanaged code.</span></span>|<span data-ttu-id="cb024-147"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> 속성.</span><span class="sxs-lookup"><span data-stu-id="cb024-147"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="cb024-148">또는</span><span class="sxs-lookup"><span data-stu-id="cb024-148">- or -</span></span><br /><br /> <span data-ttu-id="cb024-149"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> 속성.</span><span class="sxs-lookup"><span data-stu-id="cb024-149"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="cb024-150">또는</span><span class="sxs-lookup"><span data-stu-id="cb024-150">- or -</span></span><br /><br /> <span data-ttu-id="cb024-151"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> 속성.</span><span class="sxs-lookup"><span data-stu-id="cb024-151"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="cb024-152">뷰 될 때까지 메모리를 할당 지연 만들어집니다 (비지속형 파일만 해당).</span><span class="sxs-lookup"><span data-stu-id="cb024-152">To delay allocating memory until a view is created (non-persisted files only).</span></span><br /><br /> <span data-ttu-id="cb024-153">(사용 하 여 현재 시스템 페이지 크기를 결정 하려면는 <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> 속성입니다.)</span><span class="sxs-lookup"><span data-stu-id="cb024-153">(To determine the current system page size, use the <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> property.)</span></span>|<span data-ttu-id="cb024-154"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>메서드는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-154"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> method with the <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> value.</span></span><br /><br /> <span data-ttu-id="cb024-155">또는</span><span class="sxs-lookup"><span data-stu-id="cb024-155">- or -</span></span><br /><br /> <span data-ttu-id="cb024-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>포함 된 메서드는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> 열거형을 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods that have a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> enumeration as a parameter.</span></span>|  
  
### <a name="security"></a><span data-ttu-id="cb024-157">보안</span><span class="sxs-lookup"><span data-stu-id="cb024-157">Security</span></span>  
 <span data-ttu-id="cb024-158">사용 하는 다음 방법을 사용 하 여 메모리 매핑된 파일을 만들 때 액세스 권한을 적용할 수 있습니다는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> 열거형을 매개 변수로:</span><span class="sxs-lookup"><span data-stu-id="cb024-158">You can apply access rights when you create a memory-mapped file, by using the following methods that take a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> enumeration as a parameter:</span></span>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="cb024-159">사용 하 여 기존의 메모리 매핑된 파일을 열기 위한 액세스 권한을 지정할 수 있습니다는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> 사용 하는 메서드는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-159">You can specify access rights for opening an existing memory-mapped file by using the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> methods that take an <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> as a parameter.</span></span>  
  
 <span data-ttu-id="cb024-160">또한 포함할 수 있습니다는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> 미리 정의 된 액세스 규칙을 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-160">In addition, you can include a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> object that contains predefined access rules.</span></span>  
  
 <span data-ttu-id="cb024-161">새롭거나 변경 된 액세스 규칙에 메모리 매핑된 파일을 적용 하려면 사용 하 여는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="cb024-161">To apply new or changed access rules to a memory-mapped file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> method.</span></span> <span data-ttu-id="cb024-162">액세스 또는 검색 하려면 감사 기존 파일에서 규칙을 사용 하 여는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="cb024-162">To retrieve access or audit rules from an existing file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cb024-163">예제</span><span class="sxs-lookup"><span data-stu-id="cb024-163">Examples</span></span>  
  
### <a name="persisted-memory-mapped-files"></a><span data-ttu-id="cb024-164">지속형된 메모리 매핑된 파일</span><span class="sxs-lookup"><span data-stu-id="cb024-164">Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="cb024-165"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> 메서드 디스크에 기존 파일에서 메모리 매핑된 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-165">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> methods create a memory-mapped file from an existing file on disk.</span></span>  
  
 <span data-ttu-id="cb024-166">다음 예제에서는 매우 큰 파일의 일부에 대 한 메모리 매핑된 뷰를 만들고 그 일부를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-166">The following example creates a memory-mapped view of a part of an extremely large file and manipulates a portion of it.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 <span data-ttu-id="cb024-167">다음 예제에서는 다른 프로세스에서 동일한 메모리 매핑된 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-167">The following example opens the same memory-mapped file for another process.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a><span data-ttu-id="cb024-168">메모리 매핑된 파일 비지속형</span><span class="sxs-lookup"><span data-stu-id="cb024-168">Non-Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="cb024-169"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> 및 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> 메서드 디스크에 있는 기존 파일에 매핑되지 않은 메모리 매핑된 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-169">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> and <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods create a memory-mapped file that is not mapped to an existing file on disk.</span></span>  
  
 <span data-ttu-id="cb024-170">다음 예제에서는 메모리 매핑된 파일에 부울 값을 작성 하는 세 가지 별도 프로세스 (콘솔 응용 프로그램) 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-170">The following example consists of three separate processes (console applications) that write Boolean values to a memory-mapped file.</span></span> <span data-ttu-id="cb024-171">다음 작업 순서에 따라 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-171">The following sequence of actions occur:</span></span>  
  
1.  <span data-ttu-id="cb024-172">`Process A`메모리 매핑된 파일을 만들고 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-172">`Process A` creates the memory-mapped file and writes a value to it.</span></span>  
  
2.  <span data-ttu-id="cb024-173">`Process B`메모리 매핑된 파일을 열고는 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-173">`Process B` opens the memory-mapped file and writes a value to it.</span></span>  
  
3.  <span data-ttu-id="cb024-174">`Process C`메모리 매핑된 파일을 열고는 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-174">`Process C` opens the memory-mapped file and writes a value to it.</span></span>  
  
4.  <span data-ttu-id="cb024-175">`Process A`페이지를 읽고 메모리 매핑된 파일의 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-175">`Process A` reads and displays the values from the memory-mapped file.</span></span>  
  
5.  <span data-ttu-id="cb024-176">후 `Process A` 가 완료 된 메모리 매핑된 파일에 파일은 가비지 수집에서 회수 즉시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-176">After `Process A` is finished with the memory-mapped file, the file is immediately reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="cb024-177">이 예제를 실행 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-177">To run this example, do the following:</span></span>  
  
1.  <span data-ttu-id="cb024-178">응용 프로그램을 컴파일하고 세 개의 명령 프롬프트 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-178">Compile the applications and open three Command Prompt windows.</span></span>  
  
2.  <span data-ttu-id="cb024-179">첫 번째 명령 프롬프트 창에서 실행 `Process A`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-179">In the first Command Prompt window, run `Process A`.</span></span>  
  
3.  <span data-ttu-id="cb024-180">두 번째 명령 프롬프트 창에서 실행 `Process B`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-180">In the second Command Prompt window, run `Process B`.</span></span>  
  
4.  <span data-ttu-id="cb024-181">으로 돌아와서 `Process A` ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-181">Return to `Process A` and press ENTER.</span></span>  
  
5.  <span data-ttu-id="cb024-182">세 번째 명령 프롬프트 창에서 실행 `Process C`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-182">In the third Command Prompt window, run `Process C`.</span></span>  
  
6.  <span data-ttu-id="cb024-183">으로 돌아와서 `Process A` ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-183">Return to `Process A` and press ENTER.</span></span>  
  
 <span data-ttu-id="cb024-184">출력 `Process A` 는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb024-184">The output of `Process A` is as follows:</span></span>  
  
```  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 <span data-ttu-id="cb024-185">**프로세스 A**</span><span class="sxs-lookup"><span data-stu-id="cb024-185">**Process A**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 <span data-ttu-id="cb024-186">**프로세스 B**</span><span class="sxs-lookup"><span data-stu-id="cb024-186">**Process B**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 <span data-ttu-id="cb024-187">**C 프로세스**</span><span class="sxs-lookup"><span data-stu-id="cb024-187">**Process C**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cb024-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb024-188">See Also</span></span>  
 [<span data-ttu-id="cb024-189">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="cb024-189">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
