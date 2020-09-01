# calculadora

import React,{useState} from 'react'
import {Text, View, TextInput, Button, StyleSheet, Alert} from 'react-native'

class Calculadora{

    static Somar(valorA, valorB){
        return (parseInt(valorA) + parseInt(valorB))
    }
    
    static Subtrair(valorA, valorB){
        return (parseInt(valorA) - parseInt(valorB))
    }
    
    static Multiplicar(valorA, valorB){
        return (parseInt(valorA) * parseInt(valorB))
    }
    
    static Dividir(valorA, valorB){

        if (valorB == 0){
            return ("Impossivel dividir por zero")
        }
        else{
            return (parseInt(valorA) / parseInt(valorB))
        }    
    }
}

//export default props => {
export default function App(){
  
    const [valorA, setvalorA] = useState('')
    const [valorB, setvalorB] = useState('')
    const [resposta, setResposta] = useState('')

    return (
        <View>
            <Text style={styles.text}> Informe os seguintes dados:</Text>
            
            
            <TextInput
                placeholder="Digite o valor 1"
                value={valorA}           
                onChangeText={valorA => setvalorA(valorA)}
            />
            <TextInput
                placeholder="Digite o valor 2"
                value={valorB}
                onChangeText={valorB => setvalorB(valorB)}
            />
            <Text> Resposta = {resposta} </Text>
            <Button title="Somar" onPress={()=>{setResposta(Calculadora.Somar(valorA, valorB))}} />
            <Button title="Subtrair" onPress={()=>{setResposta(Calculadora.Subtrair(valorA, valorB))}} />
            <Button title="Multiplicar" onPress={()=>{setResposta(Calculadora.Multiplicar(valorA, valorB))}} />
            <Button title="Dividir" onPress={()=>{setResposta(Calculadora.Dividir(valorA, valorB))}}/>
        </View>
    );
}

const styles = StyleSheet.create({
    text:{
        fontSize:24,
        color:'blue',
        fontWeight:'bold'
    }
})
