  
  
  constructor(private firestore: AngularFirestore) {
    const newSong: Song = {songId: '1232131', songName: 'Ducks', votes: 0};
    // this.addSongToDatabase(newSong);
    console.log('Added Song to DB');
  }

  getSoundcloudData() {
    return this.firestore.collection('soundcloud').snapshotChanges();
  }

  addSongToDatabase(data) {
    return new Promise<any>((resolve, reject) => {
      this.firestore
        .collection('soundcloud')
        .add(data)
        .then(res => {
        }, err => reject(err));
    });
  }

  updateVoteCount(data) {
    return this.firestore
      .collection('soundcloud')
      .doc(data.payload.doc.id)
      .set({completed: true}, {merge: true});
  }
