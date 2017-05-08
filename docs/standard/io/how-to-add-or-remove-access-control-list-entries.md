---
title: "방법: 액세스 제어 목록 항목 추가 또는 제거 | Microsoft Docs"
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
  - "액세스 제어 항목[.NET Framework]"
  - "액세스 제어 목록[.NET Framework]"
  - "ACE[.NET Framework]"
  - "ACL[.NET Framework]"
  - "I/O[.NET Framework], 액세스 제어 목록 항목"
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 액세스 제어 목록 항목 추가 또는 제거
파일에서 ACL\(액세스 제어 목록\) 항목을 추가 또는 제거하려면 파일 또는 디렉터리에서 <xref:System.Security.AccessControl.FileSecurity> 또는 <xref:System.Security.AccessControl.DirectorySecurity> 개체를 가져오고 수정한 다음 파일 또는 디렉터리에 다시 적용해야 합니다.  
  
### 파일에서 ACL 항목을 추가 또는 제거하려면  
  
1.  <xref:System.IO.File.GetAccessControl%2A> 메서드를 호출하여 파일의 현재 ACL 항목을 포함하는 <xref:System.Security.AccessControl.FileSecurity> 개체를 가져옵니다.  
  
2.  1단계에서 반환된 <xref:System.Security.AccessControl.FileSecurity> 개체에서 ACL 항목을 추가 또는 제거합니다.  
  
3.  <xref:System.Security.AccessControl.FileSecurity> 개체를 <xref:System.IO.File.SetAccessControl%2A> 메서드에 전달하여 변경 내용을 적용합니다.  
  
### 디렉터리에서 ACL 항목을 추가 또는 제거하려면  
  
1.  <xref:System.IO.Directory.GetAccessControl%2A> 메서드를 호출하여 디렉터리의 현재 ACL 항목을 포함하는 <xref:System.Security.AccessControl.DirectorySecurity> 개체를 가져옵니다.  
  
2.  1단계에서 반환된 <xref:System.Security.AccessControl.DirectorySecurity> 개체에서 ACL 항목을 추가 또는 제거합니다.  
  
3.  <xref:System.Security.AccessControl.DirectorySecurity> 개체를 <xref:System.IO.Directory.SetAccessControl%2A> 메서드에 전달하여 변경 내용을 적용합니다.  
  
## 예제  
 [!code-cpp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/cpp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/cpp/sample.cpp#1)]
 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
  
## 코드 컴파일  
 이 예제를 실행하려면 유효한 사용자 또는 그룹 계정을 제공해야 합니다.  이 예제에서는 <xref:System.IO.File> 개체를 사용합니다. 그러나 <xref:System.IO.FileInfo>, <xref:System.IO.Directory> 및 <xref:System.IO.DirectoryInfo> 클래스에 동일한 절차가 사용됩니다.