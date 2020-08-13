# video-converter-tron

A video converter app created via electron

---
## Notes on code for myself
- mainWindow will communicate to the electron app (ask for info about the video)
    - mainWindow (`ipcRenderer.send`) -> electron app (`ipcMain.on`)
- app will communicate back to mainWindow with info on the video via IPC
    - electron app (`mainWindow.webContents.send`) -> mainWindow (`ipcRenderer.on`)

## Logic workflow
1. User selects videos for conversion
3. Ask electron app to discover vid length (ipc)
4. Electron app uses FFMPEG to get video
5. Electron communicates this information back over

---
### Initial Setup
`npm install`
