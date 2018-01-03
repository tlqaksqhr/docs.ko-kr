---
title: "Assert 메서드 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- granting permissions, overriding security checks
- code access security, overriding security checks
- overriding security checks
- security [.NET Framework], overriding security checks
- security [.NET Framework], assertions
- asserted permissions
- Assert method
- caller security checks
- permissions [.NET Framework], overriding security checks
- permissions [.NET Framework], assertions
ms.assetid: 1e40f4d3-fb7d-4f19-b334-b6076d469ea9
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90e5d910e0d6e6f55234255ac378fa58ebf7f307
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-assert-method"></a>Assert 메서드 사용
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <xref:System.Security.CodeAccessPermission.Assert%2A>는 코드 액세스 권한 클래스 및 <xref:System.Security.PermissionSet> 클래스에서 호출할 수 있는 메서드입니다. 사용할 수 있습니다 **Assert** 사용자 코드 (및 다운스트림 호출자) 수행할 작업을 수행할 수 있는 권한이 코드의 호출자를 사용할 수 있도록 되지 않았을 수 있는 권한을 합니다. 보안 어설션은 보안 검사 중 런타임이 수행하는 일반적인 프로세스를 변경합니다. 사용 권한을 어설션하는 경우 어설션된 권한에 대해 코드의 호출자를 검사하지 않도록 보안 시스템에 지시합니다.  
  
> [!CAUTION]
>  어설션은 보안 허점을 열고 보안 제한을 적용하는 런타임 메커니즘을 저해할 수 있으므로 신중하게 사용해야 합니다.  
  
 어설션은 라이브러리가 비관리 코드를 호출하거나 라이브러리의 의도한 용도와 명확한 관련이 없는 권한이 필요한 호출을 수행하는 경우에 유용합니다. 모든 비관리 코드를 호출 해야 하는 코드에 관리 되는 예를 들어 **SecurityPermission** 와 **UnmanagedCode** 플래그를 지정 합니다. 로컬 인트라넷에서 다운로드된 코드와 같은, 로컬 컴퓨터에서 시작되지 않은 코드에는 기본적으로 이 사용 권한이 부여되지 않습니다. 따라서 로컬 인트라넷에서 다운로드된 코드가 비관리 코드를 사용하는 라이브러리를 호출할 수 있으려면 라이브러리에서 어설션된 사용 권한이 있어야 합니다. 또한 일부 라이브러리는 호출자에게 표시되지 않으며 특별한 사용 권한이 필요한 호출을 수행할 수 있습니다.  
  
 코드가 호출자로부터 완전히 숨겨지는 방식으로 리소스에 액세스하는 상황에서 어설션을 사용할 수도 있습니다. 예를 들어 라이브러리가 데이터베이스에서 정보를 얻지만 이 과정에서 컴퓨터 레지스트리의 정보도 읽는다고 가정합니다. 코드에 필요한 알 수 없습니다 있는 라이브러리를 사용 하는 개발자가 원본에 액세스할 수 없기 때문에 **RegistryPermission** 코드를 사용 하려면. 이 경우 코드의 호출자에게 레지스트리에 액세스할 수 있는 권한을 요구하는 것이 타당하거나 필요하지 않다고 결정할 경우 레지스트리를 읽을 수 있는 권한을 어설션할 수 있습니다. 이 경우에 적절 한 권한을 어설션하는 그렇게 라이브러리 없는 호출자가 **RegistryPermission** 라이브러리를 사용할 수 있습니다.  
  
 어설션은 어설션된 권한 및 다운스트림 호출자가 요청한 권한이 동일한 형식이고 요청된 권한이 어설션된 권한의 하위 집합인 경우에만 스택 워크에 영향을 줍니다. 예를 들어, 어설션 **FileIOPermission** C 드라이브와 다운스트림 요청이에 모든 파일 읽기에 대 한 **FileIOPermission** C:\Temp의 파일을 읽을 수는 어설션이 영향을 줄 수는 스택 워크; 그러나 요청 된 경우 **FileIOPermission** C 드라이브에 쓰려고 어설션이 갖기 영향을 주지 않습니다.  
  
 어설션을 수행하려면 코드에 어셜션하는 권한 및 어설션을 수행하는 권한을 나타내는 <xref:System.Security.Permissions.SecurityPermission>을 둘 다 부여해야 합니다. 코드에 부여되지 않은 권한을 어설션할 수도 있지만 어설션을 통해 보안 검사가 성공하기 전에 실패하므로 어설션의 의미가 없습니다.  
  
 다음 그림과 사용 하면 어떤 일이 생기 **Assert**합니다. 다음 문이 A, B, C, E 및 F 어셈블리와 두 개의 사용 권한 P1과 P1A에 대해 true라고 가정합니다.  
  
-   P1A는 C 드라이브의 .txt 파일을 읽을 수 있는 권한을 나타냅니다.  
  
-   P1은 C 드라이브의 모든 파일을 읽을 수 있는 권한을 나타냅니다.  
  
-   P1A와 p 1은 모두 **FileIOPermission** 형식이 고 P1A는 p 1의 하위 집합입니다.  
  
-   어셈블리 E와 F에는 P1A 권한이 부여되었습니다.  
  
-   어셈블리 C에는 P1 권한이 부여되었습니다.  
  
-   어셈블리 A와 B에는 P1 및 P1A 권한이 부여되지 않았습니다.  
  
-   메서드 A는 어셈블리 A에 포함되고, 메서드 B는 어셈블리 B에 포함됩니다.  
  
 ![](../../../docs/framework/misc/media/assert.gif "어설션")  
Assert 사용  
  
 이 시나리오, 메서드는 호출 B, C B 호출, C 호출 E, E 호출에서 F 어설션 (P1 권한) C 드라이브에 파일을 읽을 수 있는 권한 및 메서드 E 권한 (P1A)는 C 드라이브의.txt 파일을 읽을 권한을 요청 합니다. F의 요청이 런타임에 발생 하면 F의 모든 호출자의 권한을 검사 하는 스택 워크가 수행 E부터 시작에 부여 P1A 권한이 있으므로 C의 어설션이 발견 됩니다, C의 권한을 검사 하는 스택 워크가 진행 됩니다. 요청된 권한(P1A)이 어설션된 권한(P1)의 하위 집합이기 때문에 스택 워크가 중지되고 보안 검사가 자동으로 성공합니다. 어셈블리 A와 B에 권한 P1A가 부여되지 않은 것은 중요하지 않습니다. P1을 어설션하여 메서드 C는 호출자에게 리소스에 액세스할 수 있는 권한이 부여되지 않은 경우에도 호출자가 P1로 보호된 리소스에 액세스할 수 있도록 합니다.  
  
 클래스 라이브러리를 디자인하고 클래스가 보호된 리소스에 액세스하는 경우 대체로 클래스의 호출자에게 적절한 권한을 요구하는 보안 요청을 수행해야 합니다. 클래스 다음에 대 한 작업을 수행 하는 경우 대부분의 호출자에 게 알고 있는 사용 권한이 없으며 호출 하 여 권한을 어설션할 수 인 경우 코드를이 호출할 수 있도록 하려면는 **Assert** 작업을 나타내는 권한 개체에서 메서드 코드에서 수행 합니다. 사용 하 여 **Assert** 정상적으로 하지 않는 수를 사용 하면 호출자가 이러한 방식으로 코드를 호출 합니다. 따라서 권한을 어설션하는 경우 구성 요소가 잘못 사용되지 않도록 사전에 적절한 보안 검사를 수행해야 합니다.  
  
 예를 들어 신뢰할 수 있는 라이브러리 클래스에 파일을 삭제하는 메서드가 있다고 가정합니다. 관리되지 않은 Win32 함수를 호출하여 파일에 액세스합니다. 호출자가 호출 코드의 **삭제** 삭제 될 파일의 이름을 전달 하는 메서드 C:\Test.txt 합니다. 내에서 **삭제** 메서드를 작성 하는 코드는 <xref:System.Security.Permissions.FileIOPermission> C:\Test.txt에 대 한 쓰기를 나타내는 개체입니다. 파일을 삭제하려면 쓰기 권한이 필요합니다. 다음 코드를 호출 하 여 명령적 보안 검사를 호출는 **FileIOPermission** 개체의 **요청** 메서드. 호출 스택의 호출자 중 하나에 이 권한이 없는 경우 <xref:System.Security.SecurityException>이 발생합니다. 예외가 발생하지 않으면 모든 호출자에게 C:\Test.txt에 액세스할 수 있는 권한이 있음을 알고 있습니다. 대부분의 호출자에 게 비관리 코드에 액세스할 권한이 없는, 다음 작성 하는 코드 생각 하므로 코드는 <xref:System.Security.Permissions.SecurityPermission> 비관리 코드를 호출할 수 있는 권한을 나타내는 개체의 호출 개체 **Assert** 메서드. 끝으로, 관리되지 않는 Win32 함수를 호출하여 C:\Text.txt를 삭제하고 호출자에게 컨트롤을 반환합니다.  
  
> [!CAUTION]
>  다른 코드가 사용자 코드를 사용하여 어설션하는 권한으로 보호된 리소스를 액세스할 수 있는 상황에서는 코드에서 어설션을 사용하지 않도록 해야 합니다. 예를 들어 호출자가 매개 변수로 이름이 지정 된 파일에 쓰는 코드에서 어설션 하지 않습니다는 **FileIOPermission** 코드가 열려 제 3 자가 잘못 사용 될 수 있으므로 파일에 쓰기 위한 합니다.  
  
 명령적 보안 구문을 사용 하는 경우 호출 된 **Assert** 동일한 메서드의 여러 권한에 대해는 메서드를 사용 하면 보안 예외를 throw 합니다. 대신 만들어야는 **PermissionSet** 개체를 호출 하 고 호출 하려는 개별 사용 권한을 전달 하는 **Assert** 에서 메서드는 **PermissionSet** 개체입니다. 호출할 수 있습니다는 **Assert** 메서드 선언적 보안 구문을 사용할 때 한 번 이상.  
  
 다음 예제에서는 재정의 보안 검사를 사용 하 여 선언적 구문을 보여 줍니다는 **Assert** 메서드. 에 **FileIOPermissionAttribute** 구문에는 두 개의 값이:는 <xref:System.Security.Permissions.SecurityAction> 열거형 및 권한 부여는 디렉터리 또는 파일의 위치입니다. 에 대 한 호출 **Assert** 에 대 한 액세스에 대 한 요청이 `C:\Log.txt` 성공 하지만 파일에 액세스할 수 있는 권한이 호출자에 게 확인 되지 않습니다.  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
  
      End Sub  
  
     <FileIOPermission(SecurityAction.Assert, All := "C:\Log.txt")> Public Sub   
      MakeLog()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now) '  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {      
      }     
      [FileIOPermission(SecurityAction.Assert, All = @"C:\Log.txt")]  
      public void MakeLog()  
      {     
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}   
```  
  
 다음 코드 조각을 사용 하 여 보안 검사를 재정의 명령적 구문을 보여는 **Assert** 메서드. 이 예제에서는의 인스턴스는 **FileIOPermission** 개체를 선언 합니다. 해당 생성자에 전달 됩니다 **FileIOPermissionAccess.AllAccess** 다음 파일의 위치를 설명 하는 문자열, 허용 되는 액세스 유형을 정의 합니다. 한 번의 **FileIOPermission** 개체를 정의 호출 하면 해당 **Assert** 보안 검사를 재정의 하는 메서드.  
  
```vb  
Option Explicit  
Option Strict  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
      End Sub 'New  
  
      Public Sub MakeLog()  
         Dim FilePermission As New FileIOPermission(FileIOPermissionAccess.AllAccess, "C:\Log.txt")  
         FilePermission.Assert()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now)  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {      
      }     
      public void MakeLog()  
      {  
         FileIOPermission FilePermission = new FileIOPermission(FileIOPermissionAccess.AllAccess,@"C:\Log.txt");   
         FilePermission.Assert();  
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Security.PermissionSet>  
 <xref:System.Security.Permissions.SecurityPermission>  
 <xref:System.Security.Permissions.FileIOPermission>  
 <xref:System.Security.Permissions.SecurityAction>  
 [특성](../../../docs/standard/attributes/index.md)  
 [코드 액세스 보안](../../../docs/framework/misc/code-access-security.md)
