# Programação de Funcionalidades

<span style="color:red">Pré-requisitos: <a href="2-Especificação do Projeto.md"> Especificação do Projeto</a></span>, <a href="3-Projeto de Interface.md"> Projeto de Interface</a>, <a href="4-Metodologia.md"> Metodologia</a>, <a href="3-Projeto de Interface.md"> Projeto de Interface</a>, <a href="5-Arquitetura da Solução.md"> Arquitetura da Solução</a>

Implementação do sistema descritas por meio dos requisitos funcionais e/ou não funcionais. Deve relacionar os requisitos atendidos os artefatos criados (código fonte) além das estruturas de dados utilizadas e as instruções para acesso e verificação da implementação que deve estar funcional no ambiente de hospedagem.

Para cada requisito funcional, pode ser entregue um artefato desse tipo


Tela de “Sign Up”
![Frame](https://github.com/user-attachments/assets/f41e53e0-cd06-49c8-b4a9-649fa606c541)
Requisito atendido
Requisito Funcional – Preencher campos para criação de cadastro no site. Obrigatório cadastro do e-mail, nome de usuário, senha e confirmação de senha e clicar em “Sign Up”. Realizar login se já tiver acesso, clicando em “Logar”. A aplicação irá direcionar para a tela compatível.


Estrutura de Dados:


import React from 'react';
import { View, Text, TextInput, Image, TouchableOpacity, StyleSheet, Dimensions, ScrollView } from 'react-native';

const { width, height } = Dimensions.get('window');

export default function App() {
  return (
    <ScrollView contentContainerStyle={styles.container}>
      {/* Header Verde */}
      <View style={styles.header}></View>

      {/* Título */}
      <Text style={styles.title}>Financel</Text>

      {/* Input de E-mail */}
      <Text style={styles.label}>E-Mail</Text>
      <TextInput
        style={styles.input}
        placeholder="example@example.com"
        placeholderTextColor="#8A9CA9"
      />

      {/* Input de Senha */}
      <Text style={styles.label}>Senha</Text>
      <View style={styles.passwordContainer}>
        <TextInput
          style={styles.inputPassword}
          placeholder="●●●●●●●●"
          secureTextEntry={true}
          placeholderTextColor="#8A9CA9"
        />
        {/* Ícone de Olho */}
        <Image
          source={{ uri: 'https://iconarchive.com/download/i103283/google/noto-emoji-objects/62857-eye.ico' }}
          style={styles.eyeIcon}
        />
      </View>

      {/* Botão de Login */}
      <TouchableOpacity style={styles.button}>
        <Text style={styles.buttonText}>Entrar</Text>
      </TouchableOpacity>

      {/* Esqueceu sua senha */}
      <TouchableOpacity>
        <Text style={styles.forgotPassword}>Esqueceu sua senha?</Text>
      </TouchableOpacity>

      {/* Botão de Inscrever-se */}
      <TouchableOpacity style={styles.registerButton}>
        <Text style={styles.registerButtonText}>Inscrever-Se</Text>
      </TouchableOpacity>

      {/* Impressão digital */}
      <Text style={styles.fingerprintText}>Use Impressão Digital Para Acessar</Text>

      {/* ou cadastre-se com */}
      <Text style={styles.orSignUp}>ou cadastre-se com</Text>

      {/* Botões de Login Social */}
      <View style={styles.socialButtons}>
        <TouchableOpacity>
          <Image
            source={{ uri: 'https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg' }}
            style={styles.socialIcon}
          />
          
        </TouchableOpacity>

        <TouchableOpacity>
          <Image
            source={{ uri: 'https://upload.wikimedia.org/wikipedia/commons/4/4f/Google_2015_logo.svg' }}
            style={styles.socialIcon}
          />
        </TouchableOpacity>
      </View>

      {/* Texto de Inscrição */}
      <TouchableOpacity>
        <Text style={styles.register}>Não tem uma conta? Inscrever-se</Text>
      </TouchableOpacity>
    </ScrollView>
  );
}

const styles = StyleSheet.create({
  container: {
    flexGrow: 1,
    backgroundColor: '#EAF5EC',
    paddingHorizontal: 20,
    justifyContent: 'center',
    alignItems: 'center',
  },
  header: {
    backgroundColor: '#24C996',
    height: height * 0.3,  
    width: '110%',
    borderBottomLeftRadius: 50,
    borderBottomRightRadius: 50,
    position: 'absolute',
    top: 0,
  },
  title: {
    fontSize: 32,
    fontWeight: 'bold',
    color: '#1C3D3D',
    marginTop: height * 0.15, 
    textAlign: 'center',
    marginBottom: 30,
  },
  label: {
    alignSelf: 'flex-start',
    color: '#1C3D3D',
    fontSize: 16,
    marginBottom: 5,
  },
  input: {
    width: '100%',
    padding: 15,
    backgroundColor: '#D5EADC',
    borderRadius: 10,
    color: '#2C3E50',
    marginBottom: 20,
  },
  passwordContainer: {
    width: '100%',
    flexDirection: 'row',
    alignItems: 'center',
    marginBottom: 20,
  },
  inputPassword: {
    flex: 1,
    padding: 15,
    backgroundColor: '#D5EADC',
    borderRadius: 10,
    color: '#2C3E50',
  },
  eyeIcon: {
    width: 25,
    height: 25,
    marginLeft: -40,
  },
  button: {
    width: '100%',
    padding: 15,
    backgroundColor: '#24C996',
    borderRadius: 10,
    alignItems: 'center',
    marginBottom: 10,
  },
  buttonText: {
    color: '#fff',
    fontWeight: 'bold',
    fontSize: 18,
  },
  forgotPassword: {
    alignSelf: 'center',
    color: '#1C3D3D',
    marginBottom: 20,
  },
  registerButton: {
    width: '100%',
    padding: 15,
    backgroundColor: '#D5EADC',
    borderRadius: 10,
    alignItems: 'center',
    marginBottom: 20,
  },
  registerButtonText: {
    color: '#24C996',
    fontWeight: 'bold',
    fontSize: 18,
  },
  fingerprintText: {
    color: '#1C3D3D',
    textAlign: 'center',
    marginBottom: 20,
  },
  orSignUp: {
    color: '#1C3D3D',
    textAlign: 'center',
    marginBottom: 20,
  },
  socialButtons: {
    flexDirection: 'row',
    justifyContent: 'space-around',
    width: '50%',
    marginBottom: 20,
  },
  socialIcon: {
    width: 40,
    height: 40,
  },
  register: {
    color: '#1C3D3D',
    textAlign: 'center',
  },
});



> **Links Úteis**:
>
> - [Trabalhando com HTML5 Local Storage e JSON](https://www.devmedia.com.br/trabalhando-com-html5-local-storage-e-json/29045)
> - [JSON Tutorial](https://www.w3resource.com/JSON)
> - [JSON Data Set Sample](https://opensource.adobe.com/Spry/samples/data_region/JSONDataSetSample.html)
> - [JSON - Introduction (W3Schools)](https://www.w3schools.com/js/js_json_intro.asp)
> - [JSON Tutorial (TutorialsPoint)](https://www.tutorialspoint.com/json/index.htm)
