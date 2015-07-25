# Singer.php #

<code>

namespace App;
use Illuminate\Database\Eloquent\Model;
class Singer extends Model
{
     /**
     * The database table used by the model.
     *
     * @var string
     */
    protected $table = 'singers';
    
    /**
         * Get the song record associated with the singer.
         */
        public function song()
        {
            return $this->hasOne('App\Song');
        }
    
}


</code>
