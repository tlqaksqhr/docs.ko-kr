---
title: Windows Forms에서 컨트롤 사용 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, controls
- controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: fddbe951-4485-459d-a5fd-665ea346dbc1
ms.openlocfilehash: 629a08a090178ffb1df1e9905182c9f246537533
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537364"
---
# <a name="overview-of-using-controls-in-windows-forms"></a><span data-ttu-id="bd809-102">Windows Forms에서 컨트롤 사용 개요</span><span class="sxs-lookup"><span data-stu-id="bd809-102">Overview of Using Controls in Windows Forms</span></span>
<span data-ttu-id="bd809-103">이 항목 Windows Forms 응용 프로그램의 필수 요소에 설명 하 고 컨트롤을 사용 하는 Windows Forms 응용 프로그램의 이벤트를 처리 하는 간단한 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd809-103">This topic describes the essential elements of a Windows Forms application and provides a simple example that uses controls and handles events in a Windows Forms application.</span></span>  
  
## <a name="simple-windows-forms-applications"></a><span data-ttu-id="bd809-104">간단한 Windows Forms 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="bd809-104">Simple Windows Forms Applications</span></span>  
 <span data-ttu-id="bd809-105">Windows Forms 응용 프로그램에는 최소한 다음과 같은 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd809-105">At a minimum, a Windows Forms application consists of the following elements:</span></span>  
  
-   <span data-ttu-id="bd809-106">파생 되는 하나 이상의 클래스 <xref:System.Windows.Forms.Form?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="bd809-106">One or more classes that derive from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="bd809-107">A `Main` 메서드를 호출 하는 `static` (`shared` Visual basic에서) <xref:System.Windows.Forms.Application.Run%2A> 메서드와 전달은 <xref:System.Windows.Forms.Form> 를 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="bd809-107">A `Main` method that invokes the `static` (`shared` in Visual Basic) <xref:System.Windows.Forms.Application.Run%2A> method and passes a <xref:System.Windows.Forms.Form> instance to it.</span></span> <span data-ttu-id="bd809-108"><xref:System.Windows.Forms.Application.Run%2A> 메서드는 운영 체제에서 응용 프로그램에 메시지를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd809-108">The <xref:System.Windows.Forms.Application.Run%2A> method processes messages from the operating system to the application.</span></span>  
  
 <span data-ttu-id="bd809-109">다음 코드 예제는 Windows Forms 응용 프로그램의 필수 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd809-109">The following code example shows the essential elements of a Windows Forms application.</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
  
Public Class MyForm  
   Inherits Form  
  
   Public Sub New()  
      Me.Text = "Hello World"  
   End Sub 'New  
  
   <STAThread()> _  
   Public Shared Sub Main()  
      Dim aform As New MyForm()  
      ' The Application.Run method processes messages from the operating system   
      ' to your application. If you comment out the next line of code,   
      ' your application will compile and execute, but because it is not in the  
      ' message loop, it will exit after an instance of the form is created.  
      Application.Run(aform)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
  
public class MyForm : Form {  
  
   public MyForm() {  
      this.Text = "Hello World";  
   }  
   [STAThread]  
   public static void Main(string[] args) {  
     MyForm aform = new MyForm();  
// The Application.Run method processes messages from the operating system   
// to your application. If you comment out the next line of code,   
// your application will compile and execute, but because it is not in the // message loop, it will exit after an instance of the form is created.  
      Application.Run(aform);  
   }  
}  
```  
  
## <a name="using-controls-in-a-windows-forms-application"></a><span data-ttu-id="bd809-110">Windows Forms 응용 프로그램에서 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="bd809-110">Using Controls in a Windows Forms Application</span></span>  
 <span data-ttu-id="bd809-111">다음 코드 예제에서는 Windows Forms 응용 프로그램 컨트롤을 사용 하 고 이벤트를 처리 하는 방법을 보여 주는 간단한 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd809-111">The following code example shows a simple application that illustrates how Windows Forms applications use controls and handle events.</span></span> <span data-ttu-id="bd809-112">이 예제에서는 세 개의 단추가 폼에서 구성 됩니다. 각 단추 클릭 했을 때 배경색을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd809-112">The example consists of three buttons on a form; each button changes the background color when clicked.</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.ComponentModel  
Imports System.Windows.Forms  
Imports System.Resources  
Imports System.Drawing  
  
Public Class MyForm  
   Inherits Form  
   Private red As Button  
   Private blue As Button  
   Private green As Button  
  
   Public Sub New()  
      InitializeComponent()  
   End Sub  
  
   Protected Overloads Overrides Sub Dispose(disposing as Boolean)  
      MyBase.Dispose(disposing)  
   End Sub  
  
   ' InitializeComponent is a helper method for the constructor.   
   ' It is included for consistency with code that is   
   ' auto-generated by the Windows Forms designer in Visual Studio.   
   Private Sub InitializeComponent()  
  
      ' Creates three buttons, sets their properties, and attaches  
      ' an event handler to each button.  
      red = New Button()  
      red.Text = "Red"  
      red.Location = New Point(100, 50)  
      red.Size = New Size(50, 50)  
      AddHandler red.Click, AddressOf button_Click  
      Controls.Add(red)  
  
      blue = New Button()  
      blue.Text = "Blue"  
      blue.Location = New Point(100, 100)  
      blue.Size = New Size(50, 50)  
      AddHandler blue.Click, AddressOf button_Click  
      Controls.Add(blue)  
  
      green = New Button()  
      green.Text = "Green"  
      green.Location = New Point(100, 150)  
      green.Size = New Size(50, 50)  
      AddHandler green.Click, AddressOf button_Click  
      Controls.Add(green)  
   End Sub  
  
   ' Event handler.  
   Private Sub button_Click(sender As Object, e As EventArgs)  
      If sender Is red Then  
         Me.BackColor = Color.Red  
      Else  
         If sender Is blue Then  
            Me.BackColor = Color.Blue  
         Else  
            Me.BackColor = Color.Green  
         End If  
      End If   
   End Sub  
  
   ' The STAThreadAttribute informs the common language runtime that  
   ' Windows Forms uses the single-threaded apartment model.  
   <STAThread()> _  
   Public Shared Sub Main()  
      Application.Run(New MyForm())  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.ComponentModel;  
using System.Windows.Forms;  
using System.Resources;  
using System.Drawing;  
  
public class MyForm : Form {  
   private Button red;  
   private Button blue;  
   private Button green;  
  
   public MyForm() : base() {     
      InitializeComponent();     
   }  
  
   protected override void Dispose(bool disposing) {  
      base.Dispose(disposing);  
   }  
  
// InitializeComponent is a helper method for the constructor.   
// It is included for consistency with code that is   
// auto-generated by the Windows Forms designer in Visual Studio.   
   private void InitializeComponent() {  
  
// A delegate for the click event of a button. The argument to   
// the constructor contains a reference to the method that performs the   
// event handling logic.  
      EventHandler handler = new EventHandler(button_Click);  
  
// Creates three buttons, sets their properties, and attaches  
// an event handler to each button.  
  
      red = new Button();  
      red.Text = "Red";  
      red.Location = new Point(100, 50);  
      red.Size = new Size(50, 50);  
      red.Click +=handler;  
      Controls.Add(red);  
  
      blue = new Button();  
      blue.Text = "Blue";  
      blue.Location = new Point(100, 100);  
      blue.Size = new Size(50, 50);  
      blue.Click += handler;  
      Controls.Add(blue);  
  
      green = new Button();  
      green.Text = "Green";  
      green.Location = new Point(100, 150);  
      green.Size = new Size(50, 50);  
      green.Click += handler;  
      Controls.Add(green);        
      }  
  
   // Event handler.  
   private void button_Click(object sender, EventArgs e) {  
            if (sender == red) this.BackColor = Color.Red ;  
                  else if (sender == blue) this.BackColor = Color.Blue;  
                  else this.BackColor = Color.Green;  
        }  
   // The STAThreadAttribute informs the common language runtime that  
   // Windows Forms uses the single-threaded apartment model.  
  [STAThread]  
   public static void Main(string[] args) {  
   Application.Run(new MyForm());  
   }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd809-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd809-113">See Also</span></span>  
 [<span data-ttu-id="bd809-114">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="bd809-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="bd809-115">Windows Forms 컨트롤 개발 기본 사항</span><span class="sxs-lookup"><span data-stu-id="bd809-115">Windows Forms Control Development Basics</span></span>](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)
