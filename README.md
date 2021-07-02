# create-elm-app-with-tailwind

Small experiment.

These are the steps I found to setup tailwind with `create-elm-app`:

- Add dependencies.
```
yarn add tailwindcss postcss autoprefixer
```

- Setup tailwind config
``` 
cat <<EOT > tailwind.config.js
module.exports = {
	  purge: [
                './src/**/*.html',
                './src/**/*.elm',
	  ],
	  theme: {},
	  variants: {},
	  plugins: []
}
EOT
```
- Setup postcss config
```
cat <<EOT > postcss.config.js
module.exports = {
    plugins: [
      require('tailwindcss')('./tailwind.config.js'),
      require("autoprefixer")
    ],
  };
EOT
```

- Setup css. This step appends to the css file. If you something there, you may want to clean it up.
``` 
cat <<EOT >> src/main.css
@tailwind base;

@tailwind components;

@tailwind utilities;
EOT
```

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/Qu4tro/create-elm-app-with-tailwind)
