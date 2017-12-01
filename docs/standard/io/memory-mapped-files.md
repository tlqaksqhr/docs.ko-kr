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
# <a name="memory-mapped-files"></a>메모리 매핑된 파일
메모리 매핑된 파일에는 가상 메모리에 있는 파일의 내용이 포함됩니다. 파일 및 메모리 공간 간의이 매핑을 통해 응용을 프로그램을 여러 프로세스를 포함 하는 메모리에 직접 읽고 파일을 수정 수 있습니다. 부터는 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], 관리 되는 코드를 사용 하 여에 설명 된 대로 메모리 매핑된 파일에는 네이티브 Windows 함수 메모리 매핑된 파일에 액세스 하는 것과 같은 방식으로 액세스할 수 [Win32에](http://go.microsoft.com/fwlink/?linkid=180801)합니다.  
  
 메모리 매핑된 파일에는 다음과 같은 두 종류가 있습니다.  
  
-   지속형된 메모리 매핑된 파일  
  
     지속형된 파일은 원본 디스크의 파일에는 연관 된 메모리 매핑된 파일입니다. 마지막 프로세스 작업 파일을 마치고 나면, 데이터 디스크에 소스 파일에 저장 됩니다. 이러한 메모리 매핑된 파일은 매우 큰 소스 파일 작업에 적합 합니다.  
  
-   비지속형 메모리 매핑된 파일  
  
     비지속형 파일은 파일을 디스크에 연결 되지 않은 메모리 매핑된 파일입니다. 마지막 프로세스 파일 작업을 마치고 나면, 데이터 손실 되 고 해당 파일이 가비지 수집에 의해 회수 됩니다. 이러한 파일은 프로세스 간 통신 (IPC)에 대 한 공유 메모리를 만들기에 적합 합니다.  
  
## <a name="processes-views-and-managing-memory"></a>프로세스, 뷰 및 메모리 관리  
 여러 프로세스에서 메모리 매핑된 파일을 공유할 수 있습니다. 프로세스는 파일을 만든 프로세스에 의해 할당 된 일반 이름을 사용 하 여 동일한 메모리 매핑된 파일에 매핑할 수 있습니다.  
  
 메모리 매핑된 파일을 사용 하려면의 일부 또는 전체 메모리 매핑된 파일의 뷰를 만들어야 합니다. 메모리 매핑된 파일의 한 부분을 위해 여러 뷰를 만들어 동시 메모리 제한을 만들 수도 있습니다. 동시을 유지 하기 위한 두 보기에 대 한 동일한 메모리 매핑된 파일에서 만들 수 해야 합니다.  
  
 여러 뷰 파일은 메모리 (32 비트 컴퓨터에서 2GB) 매핑에 사용할 수 있는 응용 프로그램의 논리 메모리 공간의 크기 보다 큰 경우에 필요할 수도 있습니다.  
  
 두 가지 방법으로 뷰의: 스트림 액세스 뷰와 임의 액세스 보기. 스트림 액세스 뷰를 사용 하 여 파일로; 순차적 액세스를 위해 이 방법은 비지속형 파일과 IPC에 대 한 권장 됩니다. 임의 액세스 뷰가 지속형된 파일 작업에 대 한 기본 설정 됩니다.  
  
 파일은 자동으로 페이지 수로 분할 하 고 필요에 따라 액세스 되므로 메모리 매핑된 파일 운영 체제의 메모리 관리자를 통해 액세스 됩니다. 메모리 관리를 직접 처리 필요가 없습니다.  
  
 다음 그림과 방법을 여러 프로세스 점이 여러 하 고 동시에 동일한 메모리 매핑된 파일에 봅니다 겹치는 키를 누릅니다.  
  
 ![표시 뷰는 메모리 및 # 45를; 매핑된 파일입니다. ] (../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")  
여러 메모리 매핑된 파일에는 뷰를 서로 겹치는  
  
## <a name="programming-with-memory-mapped-files"></a>메모리 매핑된 파일을 사용한 프로그래밍  
 다음 표에서 메모리 매핑된 파일 개체와 해당 멤버를 사용 하기 위한 지침을 제공 합니다.  
  
|작업|메서드 또는 속성을 사용 하 여|  
|----------|----------------------------------|  
|가져올 수는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 디스크에 파일에서 지속형된 메모리 매핑된 파일을 나타내는 개체입니다.|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.|  
|가져올 수는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 비지속형 메모리 매핑된 파일 (파일 디스크에 연결 되지 않음)을 나타내는 개체입니다.|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.<br /><br /> 또는<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.|  
|가져올 수는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 기존 메모리 매핑된 파일의 (지속형 또는 비지속형) 개체입니다.|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.|  
|가져올 수는 <xref:System.IO.UnmanagedMemoryStream> 메모리 매핑된 파일에 순차적으로 액세스 보기에 대 한 개체입니다.|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.|  
|가져올 수는 <xref:System.IO.UnmanagedMemoryAccessor> 개체에 대 한 임의 액세스 보기 메모리 매핑된 파일입니다.|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> 메서드를 호출하여 생성됩니다.|  
|가져올 수는 <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> 비관리 코드와 사용할 개체입니다.|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> 속성.<br /><br /> 또는<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> 속성.<br /><br /> 또는<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> 속성.|  
|뷰 될 때까지 메모리를 할당 지연 만들어집니다 (비지속형 파일만 해당).<br /><br /> (사용 하 여 현재 시스템 페이지 크기를 결정 하려면는 <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> 속성입니다.)|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>메서드는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> 값입니다.<br /><br /> 또는<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>포함 된 메서드는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> 열거형을 매개 변수로 합니다.|  
  
### <a name="security"></a>보안  
 사용 하는 다음 방법을 사용 하 여 메모리 매핑된 파일을 만들 때 액세스 권한을 적용할 수 있습니다는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> 열거형을 매개 변수로:  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 사용 하 여 기존의 메모리 매핑된 파일을 열기 위한 액세스 권한을 지정할 수 있습니다는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> 사용 하는 메서드는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> 매개 변수로 합니다.  
  
 또한 포함할 수 있습니다는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> 미리 정의 된 액세스 규칙을 포함 하는 개체입니다.  
  
 새롭거나 변경 된 액세스 규칙에 메모리 매핑된 파일을 적용 하려면 사용 하 여는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> 메서드. 액세스 또는 검색 하려면 감사 기존 파일에서 규칙을 사용 하 여는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> 메서드.  
  
## <a name="examples"></a>예제  
  
### <a name="persisted-memory-mapped-files"></a>지속형된 메모리 매핑된 파일  
 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> 메서드 디스크에 기존 파일에서 메모리 매핑된 파일을 만듭니다.  
  
 다음 예제에서는 매우 큰 파일의 일부에 대 한 메모리 매핑된 뷰를 만들고 그 일부를 조작 합니다.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 다음 예제에서는 다른 프로세스에서 동일한 메모리 매핑된 파일을 엽니다.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a>메모리 매핑된 파일 비지속형  
 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> 및 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> 메서드 디스크에 있는 기존 파일에 매핑되지 않은 메모리 매핑된 파일을 만듭니다.  
  
 다음 예제에서는 메모리 매핑된 파일에 부울 값을 작성 하는 세 가지 별도 프로세스 (콘솔 응용 프로그램) 구성 됩니다. 다음 작업 순서에 따라 수행 됩니다.  
  
1.  `Process A`메모리 매핑된 파일을 만들고 값을 씁니다.  
  
2.  `Process B`메모리 매핑된 파일을 열고는 값을 씁니다.  
  
3.  `Process C`메모리 매핑된 파일을 열고는 값을 씁니다.  
  
4.  `Process A`페이지를 읽고 메모리 매핑된 파일의 값을 표시 합니다.  
  
5.  후 `Process A` 가 완료 된 메모리 매핑된 파일에 파일은 가비지 수집에서 회수 즉시 합니다.  
  
 이 예제를 실행 하려면 다음을 수행 합니다.  
  
1.  응용 프로그램을 컴파일하고 세 개의 명령 프롬프트 창을 엽니다.  
  
2.  첫 번째 명령 프롬프트 창에서 실행 `Process A`합니다.  
  
3.  두 번째 명령 프롬프트 창에서 실행 `Process B`합니다.  
  
4.  으로 돌아와서 `Process A` ENTER 키를 누릅니다.  
  
5.  세 번째 명령 프롬프트 창에서 실행 `Process C`합니다.  
  
6.  으로 돌아와서 `Process A` ENTER 키를 누릅니다.  
  
 출력 `Process A` 는 다음과 같습니다.  
  
```  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 **프로세스 A**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 **프로세스 B**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 **C 프로세스**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [파일 및 스트림 I/O](../../../docs/standard/io/index.md)
