```html
# <span id="name"></span>

<!-- Animação para digitar e apagar o nome -->
<script>
  const nameElement = document.getElementById("name");
  const names = ["Seu Nome", ""];
  let index = 0;
  let isDeleting = false;

  function typeAndDelete() {
    const currentName = names[index];
    const speed = isDeleting ? 50 : 150;

    if (!isDeleting && currentName.length === name.length) {
      setTimeout(() => {
        isDeleting = true;
        typeAndDelete();
      }, 1000);
      return;
    }

    const newText = isDeleting
      ? currentName.substring(0, name.length - 1)
      : currentName.substring(0, name.length + 1);

    nameElement.innerHTML = newText;

    setTimeout(typeAndDelete, speed);
  }

  typeAndDelete();
</script>

<style>
  /* Estilo para a animação */
  #name {
    font-size: 24px;
    border-right: 2px solid #333;
    padding-right: 4px;
    animation: blink-caret 0.75s step-end infinite;
  }

  @keyframes blink-caret {
    from,
    to {
      border-color: transparent;
    }
    50% {
      border-color: #333;
    }
  }
</style>
```html
