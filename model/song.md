# Song.php #

<code>


namespace App;

use Illuminate\Database\Eloquent\Model;

class Song extends Model
{
     /**
     * The database table used by the model.
     *
     * @var string
     */
    protected $table = 'songs';
    
    protected $fillable = ['user_id', 'singer_id', 'title', 'lyrics'];
    
    
    
        /**
         * Get the user that owns the phone.
         */
        public function user()
        {
            return $this->belongsTo('App\User', 'user_id');
        }
        
        /**
         * Get the singer record associated with the song.
         */
        public function singer()
        {
            return $this->belongsTo('App\Song', 'singer_id');
        }
    
    
    
}


</code>
