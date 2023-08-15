# music-player-in-python
class MusicPlayer:
    def __init__(self):
        self.playlist = []
        self.current_track = None
        self.is_playing = False

    def add_track(self, track):
        self.playlist.append(track)
        print(f"{track} added to the playlist.")

    def play(self):
        if not self.is_playing:
            if self.playlist:
                self.is_playing = True
                self.current_track = self.playlist[0]
                print(f"Playing {self.current_track}")
            else:
                print("No tracks in the playlist.")

    def pause(self):
        if self.is_playing:
            self.is_playing = False
            print(f"Paused {self.current_track}")

    def stop(self):
        if self.is_playing:
            self.is_playing = False
            print(f"Stopped {self.current_track}")
        else:
            print("No track is currently playing.")

    def show_playlist(self):
        print("Playlist:")
        for i, track in enumerate(self.playlist, start=1):
            print(f"{i}. {track}")

def main():
    player = MusicPlayer()

    while True:
        print("\nMusic Player")
        print("1. Add track to playlist")
        print("2. Play")
        print("3. Pause")
        print("4. Stop")
        print("5. Show playlist")
        print("6. Exit")

        choice = input("Enter your choice: ")

        if choice == '1':
            track = input("Enter the track name: ")
            player.add_track(track)
        elif choice == '2':
            player.play()
        elif choice == '3':
            player.pause()
        elif choice == '4':
            player.stop()
        elif choice == '5':
            player.show_playlist()
        elif choice == '6':
            print("Goodbye!")
            break
        else:
            print("Invalid choice. Try again.")

if __name__ == "__main__":
    main()
