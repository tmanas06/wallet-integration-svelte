# create-svelte

Everything you need to build a Svelte project, powered by [`create-svelte`](https://github.com/sveltejs/kit/tree/main/packages/create-svelte).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npm create svelte@latest

# create a new project in my-app
npm create svelte@latest my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

## After cloning to run this code 
### first
```bash
bun i
```
### to run
```bash
bun run dev
```

## Note
when pressed on profiles it will give error 500, because you didn't deploy it on vercel . You can do this by simpley using the below command
```bash
vercel link
```
then add the database to the vercel project
![image](https://github.com/user-attachments/assets/13718623-bc9f-4e07-87ca-2e766be24cdf)


You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.
