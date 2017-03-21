---
title: "Visual Studio (Visual Basic)에서 개체를 유지 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: f1d0b562-e349-4dce-ab5f-c05108467030
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0ff6320aee65850b8b445f445f80b4bbe2c9c254
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-persisting-an-object-in-visual-studio-visual-basic"></a>연습: Visual Studio (Visual Basic)에 개체 유지
디자인 타임에 개체의 속성을 기본값으로 설정할 수 있습니다, 있지만 런타임 시 입력 된 값 개체가 소멸 될 때 손실 됩니다. 보존 값을 저장 하 고 개체를 인스턴스화하는 다음에 검색할 수 있도록 하는 인스턴스 간 개체의 데이터 serialization을 사용할 수 있습니다.  
  
> [!NOTE]
>  Visual Basic의 이름이 나 숫자와 같은 간단한 데이터를 저장 하려면 사용할 수 있습니다는 `My.Settings` 개체입니다. 자세한 내용은 참조 [My.Settings 개체](../../../../visual-basic/language-reference/objects/my-settings-object.md)합니다.  
  
 이 연습에서는 간단한 만듭니다 `Loan` 개체 및 해당 데이터를 파일로 유지 합니다. 그런 다음 개체를 다시 만들 때 파일에서 데이터를 검색 합니다.  
  
> [!IMPORTANT]
>  이 예제 파일이 아직 없는 경우 새 파일을 만듭니다. 응용 프로그램에 파일을 만들어야 하는 경우 해당 응용 프로그램 해야 `Create` 폴더에 대 한 권한이 있습니다. 권한은은 액세스 제어 목록을 사용 하 여 설정 됩니다. 응용 프로그램에만 필요한 파일이 이미 있으면, `Write` 권한, 낮은 권한입니다. 가능한 경우, 것이 더 안전을 배포 하는 동안 파일을 만들고만 권한을 부여 `Read` (폴더에 대해 만들기 권한) 대신 단일 파일에 대 한 사용 권한. 또한 것이 더 안전 루트 폴더 또는 Program Files 폴더에 보다 사용자 폴더에 데이터를 쓰려고 합니다.  
  
> [!IMPORTANT]
>  이 예제에서는 이진 파일의 데이터를 저장합니다. 이러한 형식은 암호 또는 신용 카드 정보와 같은 중요 한 데이터에 쓰일 수 없습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 클릭합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="creating-the-loan-object"></a>대출 개체 만들기  
 첫 번째 단계를 만드는 것을 `Loan` 클래스와 클래스를 사용 하는 테스트 응용 프로그램입니다.  
  
### <a name="to-create-the-loan-class"></a>대출 클래스를 만들려면  
  
1.  새 클래스 라이브러리 프로젝트를 만들고 "LoanClass" 라는 이름을 지정 합니다. 자세한 내용은 [솔루션 및 프로젝트 만들기](http://docs.microsoft.com/visualstudio/ide/creating-solutions-and-projects)를 참조하세요.  
  
2.  **솔루션 탐색기**을 Class1 파일에 대 한 바로 가기 메뉴를 열고 선택 **이름 바꾸기**합니다. 파일을 이름 `Loan` ENTER 키를 누릅니다. 클래스 이름도 바꿉니다 파일의 이름을 바꾸면 `Loan`합니다.  
  
3.  클래스에 다음 공용 멤버를 추가 합니다.  
  
    ```vb  
    Public Class Loan  
        Implements System.ComponentModel.INotifyPropertyChanged  
  
        Public Property LoanAmount As Double  
        Public Property InterestRate As Double  
        Public Property Term As Integer  
  
        Private p_Customer As String  
        Public Property Customer As String  
            Get  
                Return p_Customer  
            End Get  
            Set(ByVal value As String)  
                p_Customer = value  
                RaiseEvent PropertyChanged(Me,  
                  New System.ComponentModel.PropertyChangedEventArgs("Customer"))  
            End Set  
        End Property  
  
        Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
          Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
  
        Public Sub New(ByVal loanAmount As Double,  
                       ByVal interestRate As Double,  
                       ByVal term As Integer,  
                       ByVal customer As String)  
  
            Me.LoanAmount = loanAmount  
            Me.InterestRate = interestRate  
            Me.Term = term  
            p_Customer = customer  
        End Sub  
    End Class  
    ```  
  
 사용 하는 간단한 응용 프로그램을 만드는 한는 `Loan` 클래스입니다.  
  
### <a name="to-create-a-test-application"></a>테스트 응용 프로그램을 만들려면  
  
1.  에 Windows Forms 응용 프로그램 프로젝트를 솔루션에 추가 하는 **파일** 메뉴 선택 **추가**,**새 프로젝트**합니다.  
  
2.  에 **새 프로젝트 추가** 대화 상자에서 선택 **Windows Forms 응용 프로그램**, 입력 및 `LoanApp` 클릭 한 다음 프로젝트의 이름으로 **확인** 대화 상자를 닫습니다.  
  
3.  **솔루션 탐색기**, LoanApp 프로젝트를 선택 합니다.  
  
4.  에 **프로젝트** 메뉴 선택 **시작 프로젝트로 설정**합니다.  
  
5.  **프로젝트** 메뉴에서 **참조 추가**를 선택합니다.  
  
6.  에 **참조 추가** 대화 상자는 **프로젝트** 탭 한 다음 LoanClass 프로젝트를 선택 합니다.  
  
7.  **확인** 을 클릭하여 대화 상자를 닫습니다.  
  
8.  디자이너에서&4; 개를 추가 <xref:System.Windows.Forms.TextBox>폼에 컨트롤을.</xref:System.Windows.Forms.TextBox>  
  
9. 코드 편집기에서 다음 코드를 추가합니다.  
  
    ```vb  
    Private WithEvents TestLoan As New LoanClass.Loan(10000.0, 0.075, 36, "Neil Black")  
  
    Private Sub Form1_Load() Handles MyBase.Load  
        TextBox1.Text = TestLoan.LoanAmount.ToString  
        TextBox2.Text = TestLoan.InterestRate.ToString  
        TextBox3.Text = TestLoan.Term.ToString  
        TextBox4.Text = TestLoan.Customer  
    End Sub  
    ```  
  
10. 에 대 한 이벤트 처리기를 추가 `PropertyChanged` 다음 코드를 사용 하 여 폼에는 이벤트:  
  
    ```vb  
    Public Sub CustomerPropertyChanged(  
          ByVal sender As Object,  
          ByVal e As System.ComponentModel.PropertyChangedEventArgs  
        ) Handles TestLoan.PropertyChanged  
  
        MsgBox(e.PropertyName & " has been changed.")  
    End Sub  
    ```  
  
 이 시점에서 빌드 및 응용 프로그램을 실행 수 있습니다. 기본 값에 `Loan` 클래스 텍스트 상자에 표시 합니다. 7.1 이자율 값 7.5에서 변경 응용 프로그램을 다시 실행 하려고 — 값 7.5의 기본값으로 되돌립니다.  
  
 실제 세계에서 이자율 주기적으로 변경 되지만 반드시 변경 될 때마다 실행 됩니다. 업데이트 이자 응용 프로그램이 실행 될 때마다 사용자를 만드는 대신 응용 프로그램의 인스턴스 간에 가장 최근의 이자율을 유지 하는 것이 좋습니다. 다음 단계에서 serialization 대출 클래스에 추가 하 여 그렇게 할는 있습니다.  
  
## <a name="using-serialization-to-persist-the-object"></a>Serialization을 사용 하 여 개체를 유지 하기 위해  
 대출 클래스에 대 한 값을 유지 하기 위해 먼저 표시 해야 사용 하 여 클래스는 `Serializable` 특성입니다.  
  
### <a name="to-mark-a-class-as-serializable"></a>클래스를 serializable로 표시 하려면  
  
-   대출 클래스에 대 한 클래스 선언을 다음과 같이 변경 합니다.  
  
    ```vb  
    <Serializable()>  
    Public Class Loan  
    ```  
  
 `Serializable` 특성 컴파일러는 파일에 유지 될 모두 클래스에 지시 합니다. 때문에 `PropertyChanged` 이벤트를 처리 하는 Windows Form 개체를 통해, serialize 할 수 없습니다. `NonSerialized` 를 유지 하지 않도록 하는 클래스 멤버를 표시 하려면 특성을 사용할 수 있습니다.  
  
### <a name="to-prevent-a-member-from-being-serialized"></a>멤버 serialize 되 고 하지 않도록 설정 하려면  
  
-   에 대 한 선언을 변경 하는 `PropertyChanged` 다음과 같이 이벤트:  
  
    ```vb  
    <NonSerialized()>  
    Event PropertyChanged As System.ComponentModel.PropertyChangedEventHandler _  
      Implements System.ComponentModel.INotifyPropertyChanged.PropertyChanged  
    ```  
  
 다음 단계 LoanApp 응용 프로그램에 serialization 코드를 추가 하는 것입니다. 클래스를 serialize 하 고 파일에 기록 하기 위해 사용 하 여는 <xref:System.IO>및 <xref:System.Xml.Serialization>네임 스페이스.</xref:System.Xml.Serialization> </xref:System.IO> 를 방지 하기 위해 정규화 된 이름을 입력 하는 데 필요한 클래스 라이브러리에 대 한 참조를 추가할 수 있습니다.  
  
### <a name="to-add-references-to-namespaces"></a>네임 스페이스에 대 한 참조를 추가 하려면  
  
-   맨 위에 다음 문을 추가 `Form1` 클래스:  
  
    ```vb  
    Imports System.IO  
    Imports System.Runtime.Serialization.Formatters.Binary  
    ```  
  
     이 경우 이진 포맷터를 사용 하는 개체를 저장 하는 이진 형식에서입니다.  
  
 다음 단계는 개체를 만들 때 파일에서 개체를 deserialize 하는 코드를 추가 하는 것입니다.  
  
### <a name="to-deserialize-an-object"></a>개체를 deserialize하려면  
  
1.  Serialize 된 데이터의 파일 이름에 대 한 클래스에는 상수를 추가 합니다.  
  
    ```vb  
    Const FileName As String = "..\..\SavedLoan.bin"  
    ```  
  
2.  코드를 수정 하는 `Form1_Load` 다음과 같이 이벤트 프로시저:  
  
    ```vb  
    Private WithEvents TestLoan As New LoanClass.Loan(10000.0, 0.075, 36, "Neil Black")  
  
    Private Sub Form1_Load() Handles MyBase.Load  
        If File.Exists(FileName) Then  
            Dim TestFileStream As Stream = File.OpenRead(FileName)  
            Dim deserializer As New BinaryFormatter  
            TestLoan = CType(deserializer.Deserialize(TestFileStream), LoanClass.Loan)  
            TestFileStream.Close()  
        End If  
  
        AddHandler TestLoan.PropertyChanged, AddressOf Me.CustomerPropertyChanged  
  
        TextBox1.Text = TestLoan.LoanAmount.ToString  
        TextBox2.Text = TestLoan.InterestRate.ToString  
        TextBox3.Text = TestLoan.Term.ToString  
        TextBox4.Text = TestLoan.Customer  
    End Sub  
    ```  
  
     먼저 확인 해야 파일이 있는지 유의 합니다. 이 특성이 있으면 만들기는 <xref:System.IO.Stream>이진 파일을 읽을 수 있는 클래스 및 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>클래스 파일을 변환 합니다.</xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> </xref:System.IO.Stream> 스트림 형식에서 대출 개체 형식으로 변환 해야 합니다.  
  
 텍스트 상자에 입력 한 데이터를 저장 하는 코드를 추가 해야 하는 다음의 `Loan` 클래스 및 다음 클래스를 파일로 serialize 해야 합니다.  
  
### <a name="to-save-the-data-and-serialize-the-class"></a>데이터를 저장 하는 클래스 serialize  
  
-   다음 코드를 추가 하는 `Form1_FormClosing` 이벤트 프로시저:  
  
    ```vb  
    Private Sub Form1_FormClosing() Handles MyBase.FormClosing  
        TestLoan.LoanAmount = CDbl(TextBox1.Text)  
        TestLoan.InterestRate = CDbl(TextBox2.Text)  
        TestLoan.Term = CInt(TextBox3.Text)  
        TestLoan.Customer = TextBox4.Text  
  
        Dim TestFileStream As Stream = File.Create(FileName)  
        Dim serializer As New BinaryFormatter  
        serializer.Serialize(TestFileStream, TestLoan)  
        TestFileStream.Close()  
    End Sub  
    ```  
  
 이 시점에서 다시 빌드 및 응용 프로그램 실행 수 있습니다. 처음에 기본값이 텍스트 상자에 표시 됩니다. 네 번째 텍스트 상자에 이름을 입력 하 고 값을 변경 하려고 합니다. 응용 프로그램을 닫고 다시 실행 합니다. 새 값이 텍스트 상자에 표시 하는 참고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)   
 [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md)
