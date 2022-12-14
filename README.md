# YouTube Notes

In this repo, I want to create a desktop app that makes it possible to take notes while watching YouTube videos (especially educational ones).

## Planned features

- [ ] Take screenshots
- [ ] Add notes to screenshots
- [ ] Generate PDF from screenshots + notes
- [ ] OCR for screenshots (useful when taking screenshots of text, e.g. slides)
- [ ] Browse

## Implementation details

This thing should be an Electron desktop app that makes use of Next.js and Vite internally. with the [yerba](https://github.com/TheoBr/yerba) template it should have been easy to set up, but I didn't even manage to get it running locally on my Linux machine due to some weird GPU-related errors amongst other errors I didn't understand lol

The project uses

- Next.js
- Typescript
- Tailwind
- Turborepo
- Vite (for Electron builds)

### Why not a traditional Web App?

I don't have the budget to set up server infrastructure to store images and PDFs. So, I guess using the local file system is the next best option. Unfortunately, there's currently no hassle-free option for file system access in a traditional web app (e.g. the [File System Access API](https://developer.mozilla.org/en-US/docs/Web/API/File_System_Access_API) looks promising, but browser support is really bad and it still requires a user to allow folder access on every page refresh, which is a suboptimal user experience, imo).

### Why Next.js in a desktop app!?

I know, one of the main strenghts of Next.js is SSR and SSG, which are both completely irrelevant for desktop environments. But I decided to use it because of other advantages such as the simple communication with the backend (especially when using [tRPC]()) and the fact that I can just use NextAuth for Google/YouTube logins and account access (which I had already figured out for another project and is something this app might benefit from sooner or later).

## Getting Started

```bash
npm install
npm run dev
```
