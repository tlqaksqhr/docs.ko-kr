---
title: "방법: MaskedTextBox 컨트롤에 데이터 바인딩 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "데이터 바인딩, MaskedTextBox 컨트롤[Windows Forms]"
  - "MaskedTextBox 컨트롤[Windows Forms]"
  - "MaskedTextBox 컨트롤[Windows Forms], 데이터 바인딩"
ms.assetid: 34b29f07-e8df-48d4-b08b-53fcca524708
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: MaskedTextBox 컨트롤에 데이터 바인딩
다른 Windows Forms 컨트롤의 경우와 마찬가지로 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤에 데이터를 바인딩할 수 있습니다.  그러나 데이터베이스에 있는 데이터의 형식이 마스크 정의에 정의된 형식과 다른 경우에는 데이터의 형식을 다시 지정해야 합니다.  다음 절차에서는 <xref:System.Windows.Forms.Binding> 클래스의 <xref:System.Windows.Forms.Binding.Format> 및 <xref:System.Windows.Forms.Binding.Parse> 이벤트로 이 작업을 수행하여 별개의 전화 번호 및 내선 번호 데이터베이스 필드를 편집 가능한 단일 필드로 표시하는 방법을 보여 줍니다.  
  
 다음 절차를 수행하려면 Northwind 샘플 데이터베이스가 설치된 SQL Server 데이터베이스에 액세스할 수 있어야 합니다.  
  
### MaskedTextBox 컨트롤에 데이터를 바인딩하려면  
  
1.  새 Windows Forms 프로젝트를 만듭니다.  
  
2.  두 개의 <xref:System.Windows.Forms.TextBox> 컨트롤을 끌어서 폼에 놓은 다음 `FirstName` 및 `LastName`이라는 이름을 지정합니다.  
  
3.  <xref:System.Windows.Forms.MaskedTextBox> 컨트롤을 끌어서 폼에 놓은 다음 `PhoneMask`라는 이름을 지정합니다.  
  
4.  `PhoneMask`의 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성을 `(000) 000-0000 x9999`로 설정합니다.  
  
5.  폼에 다음 네임스페이스 가져오기를 추가합니다.  
  
    ```csharp  
    using System.Data.SqlClient;  
    ```  
  
    ```vb  
    Imports System.Data.SqlClient  
    ```  
  
6.  폼을 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 선택합니다.  이 코드를 폼 클래스 내에 붙여넣습니다.  
  
    ```csharp  
    Binding currentBinding, phoneBinding;  
    DataSet employeesTable = new DataSet();  
    SqlConnection sc;  
    SqlDataAdapter dataConnect;  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        DoMaskBinding();  
    }  
  
    private void DoMaskBinding()  
    {  
        try  
        {  
            sc = new SqlConnection("Data Source=CLIENTUE;Initial Catalog=NORTHWIND;Integrated Security=SSPI");  
            sc.Open();  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
  
        dataConnect = new SqlDataAdapter("SELECT * FROM Employees", sc);  
        dataConnect.Fill(employeesTable, "Employees");  
  
        // Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        // before adding them to the control - otherwise, we won't get a Format event on the   
        // initial load.   
        try  
        {  
            currentBinding = new Binding("Text", employeesTable, "Employees.FirstName");  
            firstName.DataBindings.Add(currentBinding);  
  
            currentBinding = new Binding("Text", employeesTable, "Employees.LastName");  
            lastName.DataBindings.Add(currentBinding);  
  
            phoneBinding =new Binding("Text", employeesTable, "Employees.HomePhone");  
            // We must add the event handlers before we bind, or the Format event will not get called  
            // for the first record.  
            phoneBinding.Format += new ConvertEventHandler(phoneBinding_Format);  
            phoneBinding.Parse += new ConvertEventHandler(phoneBinding_Parse);  
            phoneMask.DataBindings.Add(phoneBinding);  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
    }  
    ```  
  
    ```vb  
    Dim WithEvents CurrentBinding, PhoneBinding As Binding  
    Dim EmployeesTable As New DataSet()  
    Dim sc As SqlConnection  
    Dim DataConnect As SqlDataAdapter  
  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        DoMaskedBinding()  
    End Sub  
  
    Private Sub DoMaskedBinding()  
        Try  
            sc = New SqlConnection("Data Source=SERVERNAME;Initial Catalog=NORTHWIND;Integrated Security=SSPI")  
            sc.Open()  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Exit Sub  
        End Try  
  
        DataConnect = New SqlDataAdapter("SELECT * FROM Employees", sc)  
        DataConnect.Fill(EmployeesTable, "Employees")  
  
        ' Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        ' before adding them to the control - otherwise, we won't get a Format event on the   
        ' initial load.  
        Try  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.FirstName")  
            firstName.DataBindings.Add(CurrentBinding)  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.LastName")  
            lastName.DataBindings.Add(CurrentBinding)  
            PhoneBinding = New Binding("Text", EmployeesTable, "Employees.HomePhone")  
            PhoneMask.DataBindings.Add(PhoneBinding)  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Application.Exit()  
        End Try  
    End Sub  
    ```  
  
7.  바인딩된 <xref:System.Data.DataSet>의 `PhoneNumber` 및 `Extension` 필드를 결합하고 분리하는 <xref:System.Windows.Forms.Binding.Format> 및 <xref:System.Windows.Forms.Binding.Parse> 이벤트에 대한 이벤트 처리기를 추가합니다.  
  
    ```csharp  
    private void phoneBinding_Format(Object sender, ConvertEventArgs e)  
    {  
        String ext;  
  
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        if (currentRow["Extension"] == null)   
        {  
            ext = "";  
        } else   
        {  
            ext = currentRow["Extension"].ToString();  
        }  
  
        e.Value = e.Value.ToString().Trim() + " x" + ext;  
    }  
  
    private void phoneBinding_Parse(Object sender, ConvertEventArgs e)  
    {  
        String phoneNumberAndExt = e.Value.ToString();  
  
        int extIndex = phoneNumberAndExt.IndexOf("x");  
        String ext = phoneNumberAndExt.Substring(extIndex).Trim();  
        String phoneNumber = phoneNumberAndExt.Substring(0, extIndex).Trim();  
  
        //Get the current binding object, and set the new extension manually.   
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        // Remove the "x" from the extension.  
        currentRow["Extension"] = ext.Substring(1);  
  
        //Return the phone number.  
        e.Value = phoneNumber;  
    }  
    ```  
  
    ```vb  
    Private Sub PhoneBinding_Format(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Format  
        Dim Ext As String  
  
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        If (CurrentRow("Extension") Is Nothing) Then  
            Ext = ""  
        Else  
            Ext = CurrentRow("Extension").ToString()  
        End If  
  
        e.Value = e.Value.ToString().Trim() & " x" & Ext  
    End Sub  
  
    Private Sub PhoneBinding_Parse(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Parse  
        Dim PhoneNumberAndExt As String = e.Value.ToString()  
  
        Dim ExtIndex As Integer = PhoneNumberAndExt.IndexOf("x")  
        Dim Ext As String = PhoneNumberAndExt.Substring(ExtIndex).Trim()  
        Dim PhoneNumber As String = PhoneNumberAndExt.Substring(0, ExtIndex).Trim()  
  
        ' Get the current binding object, and set the new extension manually.   
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        ' Remove the "x" from the extension.  
        CurrentRow("Extension") = CObj(Ext.Substring(1))  
  
        ' Return the phone number.  
        e.Value = PhoneNumber  
    End Sub  
    ```  
  
8.  두 개의 <xref:System.Windows.Forms.Button> 컨트롤을 폼에 추가합니다.  각각의 이름을 `previousButton`과 `nextButton`으로 지정합니다.  각 단추를 두 번 클릭하여 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 추가하고 다음 코드 예제처럼 이벤트 처리기를 채웁니다.  
  
    ```csharp  
    private void previousButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position - 1;  
    }  
  
    private void nextButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position + 1;  
    }  
    ```  
  
    ```vb  
    Private Sub PreviousButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles PreviousButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position - 1  
    End Sub  
  
    Private Sub NextButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles NextButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position + 1  
    End Sub  
    ```  
  
9. 샘플을 실행합니다.  데이터를 편집하고 **이전** 및 **다음** 단추를 사용하여 <xref:System.Data.DataSet>에 데이터가 올바르게 유지되어 있는지 확인합니다.  
  
## 예제  
 다음 코드 예제는 이전 절차를 완료한 결과를 나열하는 전체 코드입니다.  
  
 [!code-cpp[MaskedTextBoxData#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/MaskedTextBoxData/cpp/form1.cpp#1)]
 [!code-csharp[MaskedTextBoxData#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/MaskedTextBoxData/CS/form1.cs#1)]
 [!code-vb[MaskedTextBoxData#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/MaskedTextBoxData/VB/form1.vb#1)]  
  
## 코드 컴파일  
  
-   [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 또는 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 프로젝트를 만듭니다.  
  
-   이전 절차에서 설명한 대로 <xref:System.Windows.Forms.TextBox> 및 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤을 폼에 추가합니다.  
  
-   프로젝트의 기본 폼에 대한 소스 코드 파일을 엽니다.  
  
-   이 파일의 소스 코드를 이전 "Code" 섹션에 나열된 코드로 바꿉니다.  
  
-   응용 프로그램을 컴파일합니다.  
  
## 참고 항목  
 [연습: MaskedTextBox 컨트롤 사용](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)