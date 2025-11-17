Sub CreateDescriptiveSafetyAwarenessPPT()
    Dim ppt As Presentation
    Dim sld As Slide
    Dim content As Variant
    Dim i As Integer
    
    ' Expanded descriptive content
    content = Array( _
        Array("Safety Awareness in Public Places: Shopping Malls", _
              "A guide to staying safe and secure" & vbCrLf & "Awareness helps prevent accidents and risks"), _
        Array("Introduction", _
              "Malls are busy public spaces visited by thousands daily" & vbCrLf & _
              "Risks include theft, fire, health hazards, and overcrowding" & vbCrLf & _
              "Awareness ensures safety for you and others"), _
        Array("General Safety Tips", _
              "Be aware of your surroundings at all times" & vbCrLf & _
              "Keep bags and valuables close to your body" & vbCrLf & _
              "Use official entry/exit points to avoid confusion"), _
        Array("Emergency Preparedness", _
              "Know the location of emergency exits before you start shopping" & vbCrLf & _
              "Follow instructions from mall security during emergencies" & vbCrLf & _
              "Do not panic; move in an orderly manner"), _
        Array("Fire Safety", _
              "Locate fire extinguishers and alarms near shops" & vbCrLf & _
              "Never use elevators during a fire; use stairs instead" & vbCrLf & _
              "Follow evacuation routes marked by signs"), _
        Array("Theft and Pickpocketing Prevention", _
              "Keep wallets and phones in front pockets" & vbCrLf & _
              "Avoid showing large amounts of cash or jewelry" & vbCrLf & _
              "Report suspicious behavior immediately"), _
        Array("Child Safety", _
              "Always hold children’s hands in crowded areas" & vbCrLf & _
              "Give children ID/contact cards in case they get lost" & vbCrLf & _
              "Set a fixed meeting point if separated"), _
        Array("Health & Hygiene", _
              "Use hand sanitizers after touching escalators or railings" & vbCrLf & _
              "Avoid very crowded food courts to prevent infections" & vbCrLf & _
              "Follow basic hygiene while eating and shopping"), _
        Array("Escalator & Elevator Safety", _
              "Always hold the handrail while using escalators" & vbCrLf & _
              "Stand in the middle, avoid blocking the sides" & vbCrLf & _
              "Do not overcrowd elevators; wait for the next one"), _
        Array("Crowd Management", _
              "Walk calmly and avoid running in busy areas" & vbCrLf & _
              "Stay patient during peak shopping hours" & vbCrLf & _
              "Follow the crowd flow and security guidance"), _
        Array("Parking Lot Safety", _
              "Park in well-lit areas of the mall" & vbCrLf & _
              "Do not leave valuables in cars" & vbCrLf & _
              "Be cautious when walking alone at night"), _
        Array("Role of Mall Authorities", _
              "24/7 CCTV monitoring for public safety" & vbCrLf & _
              "Security staff available for emergencies" & vbCrLf & _
              "Regular safety drills and fire mock exercises"), _
        Array("Technology in Safety", _
              "Public announcement systems guide during emergencies" & vbCrLf & _
              "Emergency alert apps notify customers instantly" & vbCrLf & _
              "Digital signboards display instructions clearly"), _
        Array("Conclusion", _
              "Safety is everyone’s shared responsibility" & vbCrLf & _
              "Awareness and cooperation help reduce risks" & vbCrLf & _
              "Stay alert, calm, and supportive of others"), _
        Array("Thank You", _
              "Stay Safe, Stay Aware!" & vbCrLf & _
              "Questions & Discussions") _
    )
    
    ' Use active presentation (with your theme)
    Set ppt = ActivePresentation
    
    ' Add slides with descriptive content
    For i = LBound(content) To UBound(content)
        Set sld = ppt.Slides.Add(ppt.Slides.Count + 1, ppLayoutText)
        sld.Shapes(1).TextFrame.TextRange.Text = content(i)(0) ' Title
        sld.Shapes(2).TextFrame.TextRange.Text = content(i)(1) ' Bullets
    Next i
    
    ' === Clean up bullets ===
    Dim shp As Shape
    For Each sld In ppt.Slides
        For Each shp In sld.Shapes
            If shp.HasTextFrame Then
                If shp.TextFrame.HasText Then
                    With shp.TextFrame.TextRange.ParagraphFormat
                        .Bullet.Type = ppBulletUnnumbered
                        .Bullet.Character = 8226   ' standard dot
                        .Bullet.Font.Size = 18     ' clean size
                    End With
                End If
            End If
        Next shp
    Next sld
    
    MsgBox "✅ Descriptive Safety Awareness PPT with " & (UBound(content) + 1) & " slides created!", vbInformation, "Done"
End Sub
