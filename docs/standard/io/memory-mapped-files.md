---
title: "메모리 매핑된 파일 | Microsoft Docs"
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
  - "프로세스 간 통신"
  - "메모리 매핑 파일"
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
caps.latest.revision: 24
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 24
---
# 메모리 매핑된 파일
메모리 매핑된 파일에는 가상 메모리에 있는 파일의 내용이 포함됩니다.  파일과 메모리 공간 사이의 이 매핑을 통해 여러 프로세스를 포함한 응용 프로그램에서 메모리를 직접 읽고 쓰는 방식으로 파일을 수정할 수 있습니다.  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 부터, 관리 코드를 사용하여 네이티브 Windows 함수가 메모리 매핑된 파일에 액세스 할때와 같은 방식으로 메모리 매핑된 파일에 액세스할 수 있습니다. 이에 대해서는 MSDN 라이브러리의 [Managing Memory\-Mapped Files in Win32](http://go.microsoft.com/fwlink/?linkid=180801) 에 설명되어 있습니다.  
  
 메모리 매핑된 파일에는 다음과 같은 두 가지 형식이 있습니다.  
  
-   지속형 메모리 매핑된 파일  
  
     지속형 파일은 디스크의 소스 파일에 연결되어 메모리 매핑된 파일입니다.  마지막 프로세스에서 파일 작업을 마치고 나면 데이터가 디스크의 소스 파일에 저장됩니다.  이러한 형식의 메모리 매핑된 파일은 매우 큰 소스 파일을 사용하여 작업하는 데 적합합니다.  
  
-   비지속형 메모리 매핑된 파일  
  
     비지속형 파일은 디스크의 소스 파일에 연결되지 않은 채 메모리 매핑된 파일입니다.  마지막 프로세스에서 파일 작업을 마치고 나면 데이터가 삭제되고 가비지 수집을 통해 파일이 회수됩니다.  이러한 파일은 IPC\(프로세스 간 통신\)용 공유 메모리를 만드는 데 적합합니다.  
  
## 프로세스, 뷰 및 메모리 관리  
 메모리 매핑된 파일은 여러 프로세스에서 공유할 수 있습니다.  파일을 만든 프로세스를 통해 할당된 일반 이름을 사용하여 여러 프로세스에서 메모리 매핑된 파일 하나에 매핑할 수 있습니다.  
  
 메모리 매핑된 파일을 사용하여 작업하려면 메모리 매핑된 파일 전체 또는 일부의 뷰를 만들어야 합니다.  또한 메모리 매핑된 파일의 한 부분에 대한 뷰를 여러 개 만들어 동시 메모리를 만들 수도 있습니다.  두 개의 뷰를 동시에 유지하려면 두 뷰를 한 메모리 매핑된 파일에서 만들어야 합니다.  
  
 메모리 매핑된 파일이 메모리 매핑에 사용할 수 있는 응용 프로그램의 논리 메모리 공간 크기\(32비트 컴퓨터의 경우 2GB\)보다 클 경우 여러 개의 뷰를 사용해야 할 수도 있습니다.  
  
 뷰에는 스트림 액세스 뷰와 임의 액세스 뷰라는 두 가지 형식이 있습니다.  파일에 순차적으로 액세스하려면 스트림 액세스 뷰를 사용합니다. 이는 비지속형 파일과 IPC에 적합한 뷰입니다.  지속형 파일을 사용하여 작업하는 데는 임의 액세스 뷰가 더 적합합니다.  
  
 메모리 매핑된 파일에는 운영 체제의 메모리 관리자를 통해 액세스하므로 파일이 자동으로 여러 페이지로 분할되고 필요한 부분에 액세스하게 됩니다.  사용자가 직접 메모리를 관리할 필요가 없습니다.  
  
 다음 그림에서는 여러 프로세스가 동일한 메모리 매핑된 파일에 대한 뷰를 동시에 서로 겹치게 여러 개 가질 수 있는 방법을 보여 줍니다.  
  
 ![메모리 매핑된 파일에 대한 뷰를 보여 줍니다.](../../../docs/standard/io/media/memmappersisted.png "MemMapPersisted")  
메모리 매핑된 파일의 서로 겹치는 여러 개의 뷰  
  
## 메모리 매핑된 파일을 사용한 프로그래밍  
 다음 표에는 메모리 매핑된 파일 개체와 해당 멤버를 사용하기 위해 알아 둬야 할 지침이 나와 있습니다.  
  
|Task|사용할 메서드 또는 속성|  
|----------|-------------------|  
|디스크에 있는 파일에서 지속형 메모리 매핑된 파일을 나타내는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 개체 가져오기|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=fullName> 메서드|  
|비지속형 메모리 매핑된 파일\(디스크의 파일에 연결되지 않은 파일\)을 나타내는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 개체 가져오기|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=fullName> 메서드<br /><br /> \- 또는 \-<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=fullName> 메서드|  
|기존의 메모리 매핑된 파일\(지속형 또는 비지속형\)의 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 개체 가져오기|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=fullName> 메서드|  
|메모리 매핑된 파일에 순차적으로 액세스하는 뷰에 대한 <xref:System.IO.UnmanagedMemoryStream> 개체 가져오기|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=fullName> 메서드|  
|메모리 매핑된 파일에 무작위로 액세스하는 뷰에 대한 <xref:System.IO.UnmanagedMemoryAccessor> 개체 가져오기|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=fullName> 메서드|  
|비관리 코드에 사용할 <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> 개체 가져오기|<xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=fullName> 속성.<br /><br /> \- 또는 \-<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=fullName> 속성.<br /><br /> \- 또는 \-<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=fullName> 속성.|  
|뷰를 만들 때까지 메모리 할당 지연\(비지속형 파일에만 해당\)<br /><br /> 현재 시스템 페이지 크기를 확인하려면 <xref:System.Environment.SystemPageSize%2A?displayProperty=fullName> 속성을 사용합니다.|<xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions?displayProperty=fullName> 값이 포함된 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> 메서드<br /><br /> \- 또는 \-<br /><br /> <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> 열거형을 매개 변수로 갖는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> 메서드|  
  
### 보안  
 메모리 매핑된 파일을 만들 때 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> 열거형을 매개 변수로 갖는 다음과 같은 메서드를 사용하여 액세스 권한을 적용할 수 있습니다.  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=fullName>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=fullName>  
  
-   <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=fullName>  
  
 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights>를 매개 변수로 갖는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> 메서드를 사용하여 기존의 메모리 매핑된 파일을 여는 데 필요한 액세스 권한을 지정할 수 있습니다.  
  
 또한 미리 정의된 액세스 규칙이 들어 있는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> 개체를 포함할 수 있습니다.  
  
 메모리 매핑된 파일에 대한 액세스 규칙을 새로 만들거나 변경한 후 적용하려면 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> 메서드를 사용합니다.  기존 파일에서 액세스 또는 감사 규칙을 검색하려면 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> 메서드를 사용합니다.  
  
## 예제  
  
### 지속형 메모리 매핑된 파일  
 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> 메서드는 디스크에 있는 기존 파일에서 메모리 매핑된 파일을 만듭니다.  
  
 다음 예제에서는 매우 큰 파일의 일부에 대한 메모리 매핑된 뷰를 만들고 그 일부를 조작합니다.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 다음 예제에서는 동일한 메모리 매핑된 파일을 다른 프로세스에 대해 엽니다.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### 비지속형 메모리 매핑된 파일  
 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> 및 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> 메서드는 디스크에 있는 기존 파일에 매핑되지 않는 메모리 매핑된 파일을 만듭니다.  
  
 다음 예제는 메모리 매핑된 파일에 부울 값을 쓰는 세 개의 서로 다른 프로세스\(콘솔 응용 프로그램\)로 구성되어 있습니다.  다음과 같은 순서로 작업이 수행됩니다.  
  
1.  `Process A`에서 메모리 매핑된 파일을 만들고 이 파일에 값을 씁니다.  
  
2.  `Process B`에서 메모리 매핑된 파일을 열고 이 파일에 값을 씁니다.  
  
3.  `Process C`에서 메모리 매핑된 파일을 열고 이 파일에 값을 씁니다.  
  
4.  `Process A`에서 메모리 매핑된 파일의 값을 읽고 표시합니다.  
  
5.  `Process A`에서 메모리 매핑된 파일을 닫으면 가비지 수집에 의해 해당 파일이 즉시 회수됩니다.  
  
 이 예제를 실행하려면 다음을 수행합니다.  
  
1.  응용 프로그램을 컴파일하고 세 개의 명령 프롬프트 창을 엽니다.  
  
2.  첫째 명령 프롬프트 창에서 `Process A`를 실행합니다.  
  
3.  두 번째 명령 프롬프트 창에서 `Process B`를 실행합니다.  
  
4.  `Process A`로 돌아가 Enter 키를 누릅니다.  
  
5.  세 번째 명령 프롬프트 창에서 `Process C`를 실행합니다.  
  
6.  `Process A`로 돌아가 Enter 키를 누릅니다.  
  
 `Process A`의 출력은 다음과 같습니다.  
  
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
  
 **프로세스 C**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## 참고 항목  
 [파일 및 스트림 I\/O](../../../docs/standard/io/index.md)