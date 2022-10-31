# cpf-checker
Função de Excel e Google Sheets para verificar se CPF foi digitado corretamente

Função (Substituir "$A2" pela célula que contém o CPF):
```
=SE(
    ÉNÚM(VALOR($A2));SE(
        NÚM.CARACT($A2)=11;SE(
            OU(
                $A2="00000000000";
                $A2="11111111111";
                $A2="22222222222";
                $A2="33333333333";
                $A2="44444444444";
                $A2="55555555555";
                $A2="66666666666";
                $A2="77777777777";
                $A2="88888888888";
                $A2="99999999999"
            )=FALSO;SE(
                DIREITA(
                    MOD((SOMA(
                        (EXT.TEXTO($A2;1;1)*10);
                        (EXT.TEXTO($A2;2;1)*9);
                        (EXT.TEXTO($A2;3;1)*8);
                        (EXT.TEXTO($A2;4;1)*7);
                        (EXT.TEXTO($A2;5;1)*6);
                        (EXT.TEXTO($A2;6;1)*5);
                        (EXT.TEXTO($A2;7;1)*4);
                        (EXT.TEXTO($A2;8;1)*3);
                        (EXT.TEXTO($A2;9;1)*2);;
                    )*10);11);1)=(EXT.TEXTO($A2;10;1));SE(
                    DIREITA(
                        MOD((SOMA(
                            (EXT.TEXTO($A2;1;1)*11);
                            (EXT.TEXTO($A2;2;1)*10);
                            (EXT.TEXTO($A2;3;1)*9);
                            (EXT.TEXTO($A2;4;1)*8);
                            (EXT.TEXTO($A2;5;1)*7);
                            (EXT.TEXTO($A2;6;1)*6);
                            (EXT.TEXTO($A2;7;1)*5);
                            (EXT.TEXTO($A2;8;1)*4);
                            (EXT.TEXTO($A2;9;1)*3);
                            (EXT.TEXTO($A2;10;1)*2);
                        )*10);11);1)=(EXT.TEXTO($A2;11;1));
                        VERDADEIRO;
                    FALSO);
                FALSO);
            FALSO);
        FALSO);
    FALSO
)
```
