# Lozania
programa para calculo de valores, se desea hacer un exe del mismo para windows y android
Public Class Shelly1
    Private Sub Calcular_Click(sender As Object, e As EventArgs) Handles Calcular.Click

        Dim R As String
        Dim V As String
        Dim C As String
        V = 0
        RiesgoN.Text = 0
        Contrato.Text = 0
        Total1.Text = 0

        If ARL.Checked = True Then
            R = InputBox("Riesgo")
            RiesgoN.Text = R
            If R = 1 Then
                V = 4350
            ElseIf R = 2 Then
                V = 8650
            ElseIf R = 3 Then
                V = 20200
            ElseIf R = 4 Then
                V = 36050
            ElseIf R = 5 Then
                V = 57650
            End If
        Else
            V = V
        End If

        If Independiente.Checked = True Then
            If EPS.Checked = True Then
                V = V + 104000
            Else
                V = V
            End If
            If P.Checked = True Then
                V = V + 132500
            Else
                V = V
            End If


        ElseIf Minimo.Checked = True Then
            If EPS.Checked = True Then
                V = V + 33150
            Else
                V = V
            End If

            If P.Checked = True Then
                V = V + 132500
            Else
                V = V
            End If

            If CC.Checked = True Then
                V = V + 33150
            Else
                V = V
            End If

        Else
            C = InputBox("Valor del contrato")
            Contrato.Text = C

            If EPS.Checked = True Then
                V = (C * 100) / 5
            Else
                V = V
            End If

            If P.Checked = True Then
                V = (C * 100) / 6.4
            Else
                V = V
            End If

            If CC.Checked = True Then
                V = V
            Else
                V = V
            End If
        End If

        Total1.Text = V + 30000

    End Sub
End Class
