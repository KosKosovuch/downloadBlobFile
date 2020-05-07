export function downloadBlobFile(blob: Blob, fileName: string, format: string): void {
    // IE & EDGE
    if (window.navigator && window.navigator.msSaveBlob) {
        window.navigator.msSaveBlob(blob, `${fileName}.${format}`);
        return;
    }

    const url = URL.createObjectURL(blob);
    const link = document.createElement('a');
    link.href = url;
    link.download = `${fileName}.${format}`;
    link.style.visibility = 'hidden';
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);

    // remove object URL
    setTimeout(() => {
        URL.revokeObjectURL(url);
    }, 100);
}
