# Implementando-Uma-Tela-de-Login-Com-Valida-o-Usando-TypeScript

Implementando uma tela de login com validação usando TypeScript no React. Aqui está um exemplo básico de como podemos começar:

```typescript
import React, { useState } from 'react';

interface LoginProps {
  // Defina as propriedades necessárias, se houver
}

const Login: React.FC<LoginProps> = () => {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');
  const [isFormValid, setIsFormValid] = useState(false);

  const validateForm = () => {
    // Implemente a lógica de validação
    const emailRegex = /\S+@\S+\.\S+/;
    const isEmailValid = emailRegex.test(email);
    const isPasswordValid = password.length > 6;
    setIsFormValid(isEmailValid && isPasswordValid);
  };

  const handleSubmit = (event: React.FormEvent) => {
    event.preventDefault();
    if (isFormValid) {
      // Implemente a lógica de autenticação
      console.log('Formulário enviado:', { email, password });
    } else {
      console.log('Formulário inválido');
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <div>
        <label htmlFor="email">E-mail:</label>
        <input
          type="email"
          id="email"
          value={email}
          onChange={(e) => setEmail(e.target.value)}
          onBlur={validateForm}
        />
      </div>
      <div>
        <label htmlFor="password">Senha:</label>
        <input
          type="password"
          id="password"
          value={password}
          onChange={(e) => setPassword(e.target.value)}
          onBlur={validateForm}
        />
      </div>
      <button type="submit">Entrar</button>
    </form>
  );
};

export default Login;
```

Neste código, temos um componente funcional `Login` que utiliza o hook `useState` para gerenciar o estado do e-mail e da senha. A função `validateForm` é chamada sempre que o usuário sai de um dos campos de entrada (evento `onBlur`), e ela atualiza o estado `isFormValid` baseado na validade do e-mail e da senha. O método `handleSubmit` é chamado quando o formulário é enviado, e ele verifica se o formulário é válido antes de proceder com a lógica de autenticação.

Lembre-se de ajustar a lógica de validação e autenticação conforme as necessidades do seu projeto. 

https://github.com/digitalinnovationone/trilha-react-desafio-4
