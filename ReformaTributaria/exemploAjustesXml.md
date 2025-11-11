```
<gIBSCBS>
    <!-- Base de cálculo -->
    <vBC>800.00</vBC>

    <!-- IBS - Parcela Estadual -->
    <gIBSUF>
        <pIBSUF>1.50</pIBSUF> <!-- Alíquota nominal -->
        
        <!-- Ajuste de diferença tributária -->
        <gDif>
            <pDif>1.00</pDif> <!-- Percentual de diferença aplicado -->
            <vDif>8.00</vDif> <!-- Valor da diferença -->
        </gDif>

        <!-- Ajuste de devolução de tributo -->
        <gDevTrib>
            <vDevTrib>5.00</vDevTrib> <!-- Valor devolvido -->
        </gDevTrib>

        <!-- Ajuste de redução de alíquota -->
        <gRed>
            <pRedAliq>10.00</pRedAliq> <!-- Redução de 10% na alíquota -->
            <pAliqEfet>1.35</pAliqEfet> <!-- Alíquota efetiva final -->
        </gRed>

        <!-- Valor total após ajustes -->
        <vIBSUF>15.00</vIBSUF>
    </gIBSUF>

    <!-- IBS - Parcela Municipal -->
    <gIBSMun>
        <pIBSMun>2.00</pIBSMun>

        <gDif>
            <pDif>0.50</pDif>
            <vDif>4.00</vDif>
        </gDif>

        <gDevTrib>
            <vDevTrib>3.00</vDevTrib>
        </gDevTrib>

        <gRed>
            <pRedAliq>5.00</pRedAliq>
            <pAliqEfet>1.90</pAliqEfet>
        </gRed>

        <vIBSMun>18.00</vIBSMun>
    </gIBSMun>

    <!-- CBS - Parcela Federal -->
    <gCBS>
        <pCBS>3.00</pCBS>

        <gDif>
            <pDif>0.25</pDif>
            <vDif>2.00</vDif>
        </gDif>

        <gDevTrib>
            <vDevTrib>1.50</vDevTrib>
        </gDevTrib>

        <gRed>
            <pRedAliq>2.00</pRedAliq>
            <pAliqEfet>2.94</pAliqEfet>
        </gRed>

        <vCBS>25.00</vCBS>
    </gCBS>

    <!-- Grupo de tributo regular (sem ajustes) -->
    <gTribRegular>
        <CSTReg>000</CSTReg>
        <cClassTribReg>000000</cClassTribReg>

        <pAliqEfetRegIBSUF>1.50</pAliqEfetRegIBSUF>
        <vTribRegIBSUF>12.00</vTribRegIBSUF>

        <pAliqEfetRegIBSMun>2.00</pAliqEfetRegIBSMun>
        <vTribRegIBSMun>16.00</vTribRegIBSMun>

        <pAliqEfetRegCBS>3.00</pAliqEfetRegCBS>
        <vTribRegCBS>24.00</vTribRegCBS>
    </gTribRegular>
</gIBSCBS>

```
