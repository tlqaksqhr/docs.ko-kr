---
title: '방법: Access Control 목록 항목 추가 또는 제거'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ACEs [.NET Framework]
- ACLs [.NET Framework]
- access control entries [.NET Framework]
- I/O [.NET Framework], access control list entries
- access control lists [.NET Framework]
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 24c428a80f18b35d0aa3119a3c5fa1a6dcb2130e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-or-remove-access-control-list-entries"></a><span data-ttu-id="61c8f-102">방법: Access Control 목록 항목 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="61c8f-102">How to: Add or Remove Access Control List Entries</span></span>
<span data-ttu-id="61c8f-103">파일에서 ACL(Access Control 목록) 항목을 추가 또는 제거하려면 파일 또는 디렉터리에서 <xref:System.Security.AccessControl.FileSecurity> 또는 <xref:System.Security.AccessControl.DirectorySecurity> 개체를 가져오고 수정한 다음 파일 또는 디렉터리에 다시 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c8f-103">To add or remove Access Control List (ACL) entries to or from a file, the <xref:System.Security.AccessControl.FileSecurity> or <xref:System.Security.AccessControl.DirectorySecurity> object must be obtained from the file or directory, modified, and then applied back to the file or directory.</span></span>  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-file"></a><span data-ttu-id="61c8f-104">파일에서 ACL 항목을 추가 또는 제거하려면</span><span class="sxs-lookup"><span data-stu-id="61c8f-104">To add or remove an ACL entry from a File</span></span>  
  
1.  <span data-ttu-id="61c8f-105"><xref:System.IO.File.GetAccessControl%2A> 메서드를 호출하여 파일의 현재 ACL 항목을 포함하는 <xref:System.Security.AccessControl.FileSecurity> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="61c8f-105">Call the <xref:System.IO.File.GetAccessControl%2A> method to get a <xref:System.Security.AccessControl.FileSecurity> object that contains the current ACL entries of a file.</span></span>  
  
2.  <span data-ttu-id="61c8f-106">1단계에서 반환된 <xref:System.Security.AccessControl.FileSecurity> 개체에서 ACL 항목을 추가 또는 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="61c8f-106">Add or remove ACL entries from the <xref:System.Security.AccessControl.FileSecurity> object returned from step 1.</span></span>  
  
3.  <span data-ttu-id="61c8f-107"><xref:System.Security.AccessControl.FileSecurity> 개체를 <xref:System.IO.File.SetAccessControl%2A> 메서드에 전달하여 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="61c8f-107">Pass the <xref:System.Security.AccessControl.FileSecurity> object to the <xref:System.IO.File.SetAccessControl%2A> method to apply the changes.</span></span>  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-directory"></a><span data-ttu-id="61c8f-108">디렉터리에서 ACL 항목을 추가 또는 제거하려면</span><span class="sxs-lookup"><span data-stu-id="61c8f-108">To add or remove an ACL entry from a Directory</span></span>  
  
1.  <span data-ttu-id="61c8f-109"><xref:System.IO.Directory.GetAccessControl%2A> 메서드를 호출하여 디렉터리의 현재 ACL 항목을 포함하는 <xref:System.Security.AccessControl.DirectorySecurity> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="61c8f-109">Call the <xref:System.IO.Directory.GetAccessControl%2A> method to get a <xref:System.Security.AccessControl.DirectorySecurity> object that contains the current ACL entries of a directory.</span></span>  
  
2.  <span data-ttu-id="61c8f-110">1단계에서 반환된 <xref:System.Security.AccessControl.DirectorySecurity> 개체에서 ACL 항목을 추가 또는 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="61c8f-110">Add or remove ACL entries from the <xref:System.Security.AccessControl.DirectorySecurity> object returned from step 1.</span></span>  
  
3.  <span data-ttu-id="61c8f-111"><xref:System.Security.AccessControl.DirectorySecurity> 개체를 <xref:System.IO.Directory.SetAccessControl%2A> 메서드에 전달하여 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="61c8f-111">Pass the <xref:System.Security.AccessControl.DirectorySecurity> object to the <xref:System.IO.Directory.SetAccessControl%2A> method to apply the changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61c8f-112">예</span><span class="sxs-lookup"><span data-stu-id="61c8f-112">Example</span></span>  
 [!code-cpp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/cpp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/cpp/sample.cpp#1)]
 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="61c8f-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="61c8f-113">Compiling the Code</span></span>  
 <span data-ttu-id="61c8f-114">이 예제를 실행하려면 유효한 사용자 또는 그룹 계정을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c8f-114">You must supply a valid user or group account to run this example.</span></span> <span data-ttu-id="61c8f-115">이 예제에서는 <xref:System.IO.File> 개체를 사용합니다. 그러나 <xref:System.IO.FileInfo>, <xref:System.IO.Directory> 및 <xref:System.IO.DirectoryInfo> 클래스에 동일한 절차가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c8f-115">This example uses a <xref:System.IO.File> object; however, the same procedure is used for the <xref:System.IO.FileInfo>, <xref:System.IO.Directory>, and <xref:System.IO.DirectoryInfo> classes.</span></span>
