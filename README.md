# Clipboard Unblock Bookmarklet

Permite copiar, cortar e colar em sites que bloqueiam essas ações.  
Remove restrições impostas por scripts JavaScript e restaura o controle do usuário sobre a área de transferência.

## ⚙️ Como funciona
O script adiciona interceptadores de eventos para `copy`, `cut` e `paste` que impedem qualquer bloqueio vindo da página.  
Após ativar, o site não poderá mais barrar o uso do teclado (Ctrl+C, Ctrl+V, etc.).

## 💡 Uso
1. Crie um novo favorito no navegador.  
2. No campo de **URL**, cole o código abaixo.  
3. Em qualquer site que bloqueie copiar/colar, clique no favorito.  
4. Será exibido o alerta **“Bloqueio desativado!”** indicando que a função está ativa.

## 🧩 Código
```js
javascript:(function(){
  function disableClipboardBlocking(){
    const unblockEvent=(e)=>{e.stopImmediatePropagation();return true;};
    document.addEventListener("copy",unblockEvent,true);
    document.addEventListener("cut",unblockEvent,true);
    document.addEventListener("paste",unblockEvent,true);
    alert("Bloqueio desativado!");
  }
  disableClipboardBlocking();
})();
