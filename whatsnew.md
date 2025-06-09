# Enhanced Analytics - Appendix & Changelog

This document provides details on recent changes and outlines known limitations of the script.

## Version 2.3 (Latest)

This update focused on adding intelligence and robustness to the video tracking modules to handle more complex, real-world scenarios.

*   **YouTube Playlist Tracking:** The script now correctly tracks user progression through a YouTube playlist embed. When the player advances to the next video, the script automatically fires a `video_complete` event for the previous video and a `video_start` event for the new one, ensuring each video in the playlist is tracked as a unique session.

*   **Muted Video Detection:** A new parameter, `video_is_muted` (or `audio_is_muted`), is now included with every video and audio event. This boolean (`true`/`false`) provides crucial context for analyzing user engagement, helping to differentiate between active listening/watching and passive, muted autoplay views.

*   **Live Stream Handling:** The script now detects live streams on YouTube and with HTML5 media. When a live stream is detected, it sends a `video_is_live: true` parameter in the `video_start` event and disables percentage-based progress tracking to prevent errors and meaningless "0% progress" events.

*   **HTML5 Dynamic Source Handling:** For modern web applications that might change the source of a `<video>` or `<audio>` element without replacing the element itself, the tracker now detects this change. It correctly ends the session for the old media and begins a new one for the new source.

## Version 2.2

This version focused on improving the reliability and consistency of the core tracking modules.

*   **Improved Seek Logic:** A unified `_resetVideoMilestonesOnSeek` function was implemented to ensure that when a user seeks (jumps forward or backward) in a video, progress milestones are correctly reset. This prevents missed events and provides more accurate data across all video players (YouTube, HTML5, Vimeo).

*   **Accurate Link Click Tracking:** The auto-link tracker now only fires for primary (left) mouse clicks or the 'Enter' key, ignoring right-clicks and middle-clicks for more precise `click` event reporting.

*   **Robust URL Scrubbing:** Error handling in the URL parameter scrubbing function was improved to return a clean base URL in case of a parsing error, preventing malformed data from being sent.

## Known Limitations & Future Considerations

*   **TikTok / Instagram Embeds:** These platforms do not provide a public JavaScript API for their embeds. While the script can know an embed has loaded on the page, it cannot track interactions *within* the embed (like plays, pauses, or progress). This is a platform limitation.

*   **Time-Based Live Stream Tracking:** While the script now correctly *identifies* live streams, it does not yet offer time-based progress milestones for them (e.g., "viewed for 60 seconds"). This is a potential future enhancement.

*   **Advanced Player Interactions:** The script does not currently track finer engagement signals like volume changes (beyond muted status) or changes in playback speed.
