# Vue Quick Toastify

Vue Quick Toastify is a simple and customizable toast notification component for Vue applications.

## Installation

To install the package, run the following command:

```sh
npm install vue-quick-toastify
```
## Usage
Import the QuickToastify component and use it in your application. The component takes the following props:

- <b>isShow (boolean)</b>: Determines if the toast notification is shown.
- <b>setIsShow (function)</b>: A function to update the isShow state.
- <b>message (string)</b>: The message to display in the toast notification.
- <b>notificationType (string)</b>: The type of notification, either 'success' or 'error'.

## Example
```sh
<template>
    <button @click="isShowToastify = true">Click To show Quick Toastify</button>
    <QuickToastify 
        :isShow="isShowToaster"
        :close="hideToastify"
        :notificationType="'success'"
        :message="'Welcome to Quick Toastify☺'"
    />
</template>

<script>
    import QuickToastify from 'vue-quick-toastify';
    import 'vue-quick-toastify/dist/quick-toastify.css';
    export default{
        name:'App',
        components:{
            QuickToastify
        },
        data(){
            return{
                isShowToastify=false
            }
        },
        methods:{
            hideToastify(){
                this.isShowToastify = false;
            }
        }
    }
</script>
```

## Development
If you want to contribute or run the project locally, follow these steps:

- Clone the repository
First, clone the repository.
```sh
git clone https://github.com/CODEREXLTD/vue-quick-toastify
```
- Install dependencies
Navigate to the project directory and install the dependencies:
```sh
cd vue-quick-toastify
npm install
```
- Run server
```sh
npm run serve
```

- Build the component
```sh
npm run build
```

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

## Issues
If you encounter any issues, please report them in the [GitHub Issues](https://github.com/CODEREXLTD/vue-quick-toastify/issues) section of the repository.

## Acknowledgements
Thanks to the open-source community for their contributions and inspiration.
