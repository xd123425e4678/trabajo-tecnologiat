# trabajo-tecnologiat
// ...existing code...
function getVideoEmbed(url) {
    if (!url) return '';
    // YouTube
    let yt = url.match(/(?:youtube\.com\/watch\?v=|youtu\.be\/)([A-Za-z0-9_-]{11})/);
    if (yt) {
        return `
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/${yt[1]}" frameborder="0" allowfullscreen></iframe>
            </div>
        `;
    }
    // Vimeo
    let vimeo = url.match(/vimeo\.com\/(\d+)/);
    if (vimeo) {
        return `
            <div class="video-container">
                <iframe src="https://player.vimeo.com/video/${vimeo[1]}" frameborder="0" allowfullscreen></iframe>
            </div>
        `;
    }
    // Otros (genérico)
    return `
        <div class="video-container">
            <video src="${url}" controls style="width:100%;height:100%;"></video>
        </div>
    `;
}
// ...existing code...
