---
title: '방법: 시스템 리소스 해제(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: cbb66934833da2bd6f0b797944dbb9c4df267cfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647233"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="5d4cf-102">방법: 시스템 리소스 해제(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d4cf-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="5d4cf-103">사용할 수는 `Using` 블록 코드 블록을 종료할 때 시스템 리소스의 삭제 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4cf-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="5d4cf-104">또는 다른 구성 요소가 사용 하 여 할 많은 양의 메모리를 사용 하는 시스템 리소스를 사용 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4cf-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="5d4cf-105">코드는 작업을 마쳤을 때 데이터베이스 연결을 삭제 하기 위해</span><span class="sxs-lookup"><span data-stu-id="5d4cf-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1.  <span data-ttu-id="5d4cf-106">적절 한 포함 되어 있는지 확인 [Imports 문 (.NET Namespace 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 소스 파일의 시작 부분에서 데이터베이스 연결에 대 한 (이 경우 <xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="5d4cf-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2.  <span data-ttu-id="5d4cf-107">만들기는 `Using` 블록와 함께 `Using` 및 `End Using` 문.</span><span class="sxs-lookup"><span data-stu-id="5d4cf-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="5d4cf-108">블록 내의 데이터베이스 연결에서 설명 하는 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4cf-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3.  <span data-ttu-id="5d4cf-109">연결을 선언 하 고의 일환으로 해당 형식의 인스턴스를 만듭니다는 `Using` 문.</span><span class="sxs-lookup"><span data-stu-id="5d4cf-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="5d4cf-110">시스템 처리 되지 않은 예외가 대/소문자를 포함 하 여 블록을 종료 하는 방법에 관계 없이 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4cf-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="5d4cf-111">액세스할 수 없는 참고 `sqc` 에서 외부의 `Using` 변수 범위는 블록으로 제한 때문에 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4cf-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="5d4cf-112">COM 래퍼 열려 있는 파일 핸들 등의 시스템 리소스에 동일한 기법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d4cf-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="5d4cf-113">사용 된 `Using` 블록을 종료 한 후 다른 구성 요소에 사용할 수 있는 리소스에 확실 하 게 하려는 경우는 `Using` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="5d4cf-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d4cf-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d4cf-114">See Also</span></span>  
 <xref:System.Data.SqlClient.SqlConnection>  
 [<span data-ttu-id="5d4cf-115">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="5d4cf-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="5d4cf-116">판단 구조</span><span class="sxs-lookup"><span data-stu-id="5d4cf-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="5d4cf-117">루프 구조</span><span class="sxs-lookup"><span data-stu-id="5d4cf-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="5d4cf-118">기타 제어 구조</span><span class="sxs-lookup"><span data-stu-id="5d4cf-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="5d4cf-119">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="5d4cf-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="5d4cf-120">Using 문</span><span class="sxs-lookup"><span data-stu-id="5d4cf-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
