
<script>
let { url = '', URL: legacyURL = '' } = $props();

function toEmbedUrl(url) {
	if (!url) return '';

	const normalizedUrl =
		url.startsWith('http://') || url.startsWith('https://') ? url : `https://${url}`;

	try {
		const parsed = new globalThis.URL(normalizedUrl);
		const host = parsed.hostname.replace('www.', '');
		let videoId = '';

		if (host === 'youtu.be') {
			videoId = parsed.pathname.slice(1);
		} else if (host === 'youtube.com' || host === 'm.youtube.com') {
			if (parsed.pathname.startsWith('/embed/')) {
				videoId = parsed.pathname.split('/')[2] ?? '';
			} else {
				videoId = parsed.searchParams.get('v') ?? '';
			}
		}

		if (videoId) {
			return `https://www.youtube.com/embed/${videoId}`;
		}
	} catch {
		return normalizedUrl;
	}

	return normalizedUrl;
}

const inputUrl = $derived((url || legacyURL || '').trim());
const embedUrl = $derived(toEmbedUrl(inputUrl));
const hasUrl = $derived(inputUrl.length > 0);
const isEmbeddable = $derived(embedUrl.startsWith('https://www.youtube.com/embed/'));
</script>

{#if isEmbeddable}
	<iframe src={embedUrl} width="640" height="360" allowfullscreen title="Embedded video"></iframe>
{:else if hasUrl}
	<p>Couldn’t embed that link. Please use a valid YouTube URL.</p>
{:else}
	<p>Add a YouTube URL to display a video.</p>
{/if}